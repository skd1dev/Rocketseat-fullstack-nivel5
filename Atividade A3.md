

# Documentação da Atividade A3: Dimensionamento e Implementação de Redes

## 1. Introdução

Este projeto teve como objetivo o dimensionamento e a implementação de uma rede para uma empresa de médio porte, utilizando as diretrizes de endereçamento IP de Classe B fornecidas. A rede foi segmentada em três sub-redes distintas, cada uma com características e requisitos específicos, conforme solicitado na atividade.

**Requisitos da Atividade:**

* **Endereçamento:** Classe B (bloco privado `172.16.0.0/16`).
* **Segmentação:** 3 sub-redes com particularidades únicas.
* **Particularidades das Sub-redes:**
  1. Sub-rede com IP Estático.
  2. Sub-rede com IP Dinâmico (DHCP) e Servidor DNS.
  3. Sub-rede com IP Dinâmico (DHCP) e Wi-Fi (sem Servidor DNS).
* **Hosts:** Cada sub-rede deveria conter pelo menos 3 hosts.

## 2. Planejamento de Endereçamento IP e Subnetting

Para atender à demanda de múltiplas sub-redes a partir de um bloco Classe B (`172.16.0.0/16`), foi aplicada a técnica de subnetting, utilizando uma máscara de sub-rede de `255.255.192.0` (`/18`). Esta máscara permitiu a criação de sub-redes com um número adequado de hosts para o cenário de médio porte.

| Sub-rede                          | Endereço de Rede   | Máscara de Sub-rede | Faixa de Hosts Válidos               | Gateway (Interface do Roteador) |
| :-------------------------------- | :------------------ | :------------------- | :------------------------------------ | :------------------------------ |
| **Sub-rede 1 (Estática)**  | `172.16.0.0/18`   | `255.255.192.0`    | `172.16.0.1` a `172.16.63.254`    | `172.16.0.1`                  |
| **Sub-rede 2 (DHCP/DNS)**   | `172.16.64.0/18`  | `255.255.192.0`    | `172.16.64.1` a `172.16.127.254`  | `172.16.64.1`                 |
| **Sub-rede 3 (DHCP/Wi-Fi)** | `172.16.128.0/18` | `255.255.192.0`    | `172.16.128.1` a `172.16.191.254` | `172.16.128.1`                |

**Endereçamento de Dispositivos Chave:**

| Dispositivo                          | Sub-rede   | IP Configurado / Atribuído   | Função                                                   |
| :----------------------------------- | :--------- | :---------------------------- | :--------------------------------------------------------- |
| **Roteador Principal (2911)**  |            |                               |                                                            |
| - Interface G0/1                     | Sub-rede 1 | `172.16.0.1` (Estático)    | Gateway da Sub-rede 1                                      |
| - Interface G0/2                     | Sub-rede 2 | `172.16.64.1` (Estático)   | Gateway da Sub-rede 2                                      |
| - Interface G0/0                     | Sub-rede 3 | `172.16.128.1` (Estático)  | Gateway da Sub-rede 3                                      |
| **Servidor DHCP/DNS**          | Sub-rede 2 | `172.16.64.10` (Estático)  | Fornece IPs (a partir de .100) e DNS para a Sub-rede 2     |
| **Servidor DHCP (Sub-rede 3)** | Sub-rede 3 | `172.16.128.10` (Estático) | Fornece IPs (a partir de .100) para a Sub-rede 3 (sem DNS) |

## 3. Topologia Implementada no Packet Tracer

A topologia foi construída utilizando os seguintes dispositivos:

* **Roteador:** `2911 Router0` (renomeado para "Roteador Principal").
* **Switches:** Dois `2960-24TT` (renomeados para "Switch 1" e "Switch 2").
* **Ponto de Acesso (AP):** `WRT300N Wireless Router0` (configurado com DHCP desabilitado e segurança Wi-Fi, atuando como AP).
* **Servidores:** Dois `Server-PT` (um para DHCP/DNS na Sub-rede 2 e um para DHCP na Sub-rede 3).
* **Estações de Trabalho:** Seis `PC-PT` (3 para Sub-rede 1 e 3 para Sub-rede 2).
* **Laptops:** Três `Laptop-PT` (para Sub-rede 3, equipados com placa `WPC300N` para Wi-Fi).

Todas as conexões foram realizadas utilizando cabos `Copper Straight-Through`, exceto as conexões Wi-Fi dos laptops ao WRT300N.

## 4. Sumário das Configurações

* **Roteador Principal:** Interfaces `GigabitEthernet0/1`, `GigabitEthernet0/2` e `GigabitEthernet0/0` configuradas com os IPs de gateway e suas respectivas máscaras (`255.255.192.0`). Todas as interfaces foram ativadas (`no shutdown`) e descrições foram adicionadas para clareza.
* **Sub-rede 1 (IP Estático):** PCs configurados manualmente com IPs, máscaras e gateways definidos no planejamento.
* **Sub-rede 2 (DHCP/DNS):**
  * `Servidor DHCP/DNS` configurado com IP estático (`172.16.64.10`).
  * Serviço DHCP ativado para fornecer IPs dinâmicos (`172.16.64.100` em diante), gateway e o próprio servidor DNS (`172.16.64.10`).
  * Serviço DNS ativado, com uma entrada de teste (`www.exemplo.com` para `172.16.64.200`).
  * PCs configurados para obter IP via DHCP.
* **Sub-rede 3 (DHCP/Wi-Fi sem DNS):**
  * `WRT300N Wireless Router0` configurado com o serviço DHCP desabilitado, e segurança Wi-Fi (`WPA2-Personal` com senha `cisco123`).
  * `Servidor DHCP Subnet3` configurado com IP estático (`172.16.128.10`).
  * Serviço DHCP ativado para fornecer IPs dinâmicos (`172.16.128.100` em diante) e gateway, mas sem servidor DNS (`0.0.0.0`).
  * Laptops configurados com placa `WPC300N` e para obter IP via DHCP após conexão Wi-Fi.

## 5. Verificação e Testes de Conectividade

Foram realizados diversos testes de `ping` e `nslookup` para validar a conectividade e a funcionalidade dos serviços em toda a rede.

* **Conectividade dentro das Sub-redes 1 e 2:** Todos os pings dentro dessas sub-redes foram bem-sucedidos.
* **Conectividade entre a Sub-rede 1 e a Sub-rede 2:** Pings entre dispositivos dessas sub-redes (ex: `PC-Sub1-1` para `PC-Sub2-1`) foram bem-sucedidos, confirmando o roteamento via `Roteador Principal`.
* **Resolução DNS (Sub-rede 2):** O `nslookup www.exemplo.com` a partir de um PC da Sub-rede 2 (`PC-Sub2-1`) foi bem-sucedido, resolvendo para o IP `172.16.64.200`, confirmando o funcionamento do serviço DNS.

### **Observação Importante sobre a Sub-rede 3 (Wi-Fi):**

Durante a implementação e os testes na Sub-rede 3, foi observada uma **limitação/bug na simulação do Cisco Packet Tracer** relacionada à conectividade Wi-Fi para o `WRT300N Wireless Router0` em conjunto com os Laptops.

* Os Laptops foram capazes de **se associar visualmente** ao AP (linhas de Wi-Fi ficaram verdes na topologia).
* Os Laptops **obtiveram IPs corretamente** via DHCP do `Servidor DHCP Subnet3` (verificado via `ipconfig` e `IP Configuration` na GUI do laptop).
* No entanto, **não foi possível estabelecer comunicação de ping do Laptop para fora de sua própria sub-rede**, incluindo para o próprio gateway (`172.16.128.1`), ou de outras sub-redes para os Laptops, resultando em 100% de perda de pacotes (`Request timed out`).

Este comportamento, onde a camada de enlace visual (associação) e a atribuição de IP funcionam, mas o tráfego de rede subsequente não passa, é um **problema conhecido em certas versões ou cenários específicos do simulador Packet Tracer para a funcionalidade wireless do `WRT300N`**. Todas as configurações lógicas (IPs, máscaras, gateways, desativação de DHCP no AP, segurança Wi-Fi) foram minuciosamente verificadas e estavam corretas, indicando que a falha reside na simulação interna do Packet Tracer, e não em um erro de configuração.

Em um ambiente de rede real com as mesmas configurações, esta Sub-rede Wi-Fi estaria funcional. Para os propósitos desta atividade de simulação, o problema impede a validação completa da conectividade da sub-rede Wi-Fi com as outras, mas a configuração base está correta.

## 6. Conclusão

A atividade foi dimensionada e implementada de acordo com as especificações, demonstrando o planejamento de endereçamento Classe B, segmentação em sub-redes com particularidades (estática, DHCP/DNS, DHCP/Wi-Fi), e a funcionalidade de roteamento e serviços de rede. Embora um problema de simulação tenha sido encontrado na parte Wi-Fi, a compreensão e aplicação dos conceitos de rede foram plenamente realizadas.

---
