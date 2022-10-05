# ESQUEMA LABORATÓRIO

## Overview

<center>

| DOMÍNIO | LABVSP.LOCAL|
| :---: | :---: |
| SUBNET | 192.168.0.0 |
| MÁSCARA | 255.255.0.0 ou /16 |
| GATEWAY | 192.168.0.2 |
| DNS PRIMÁRIO | 192.168.0.3|
| NTP A | 200.160.7.186 |
| NTP B | 201.49.148.135 |

</center>

---
## HOST
Configurações de rede do laboratório (host).

<center>

| IP-01 | 192.168.0.1 |
| :---: | :---: |
| IP-02 | 192.168.255.254 |
| IP-03 | 172.16.0.1 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.1.4|
| DNS-03 | 192.168.2.4|

</center>

---

## AD
Infraestrutura de AD.

<details>
<summary>VMs</summary>

O ambiente é composto por 3 ADs, sendo o AD primário uma VM diretamente no host, e um AD secundário em cada ambiente, um no ambiente de PROD, e, outro no ambiente de DR.

<details>
<summary>AD01</summary>

AD01 se constitui do AD primário, englobando todo o ambiente.

<center>

| HOSTNAME | AD01 |
| :---: | :---: |
| USUÁRIO | Administrator |
| SENHA | zaq1@WSX |
| SO | WINDOWS SERVER 2019 |
| IP-01 | 192.168.0.3 |
| IP-02 | 172.16.0.3 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.0.2|
| RAM | 2GB |
| vCPU | 1 |
| CORES | 2 |
| DISK | 16GB |
| FQDN | ad01.labvsp.local |

</center>

</details>

---

<details>
<summary>AD02-PROD</summary>

AD02-PROD se constitui do AD secundário localizado no ambiente de PROD.

<center>

| HOSTNAME | AD02 |
| :---: | :---: |
| USUÁRIO | administrator |
| SENHA | zaq1@WSX |
| SO | WINDOWS SERVER 2019 |
| IP-01 | 192.168.1.4 |
| IP-02 | 172.16.1.4 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.1.4|
| DNS-02 | 192.168.0.3|
| RAM | 2GB |
| vCPU | 1 |
| CORES | 2 |
| DISK | 16GB |
| FQDN | ad02.prod.labvsp.local |
| AMBIENTE | PROD |
| HOST | esxi02.prod.labvsp.local |
| DATASTORE | LUN-iSCSI-01 |

</center>

</details>

---

<details>
<summary>AD02-DR</summary>

AD02-DR se constitui do AD secundário localizado no ambiente de DR.

<center>

| HOSTNAME | AD02 |
| :---: | :---: |
| USUÁRIO | administrator |
| SENHA | zaq1@WSX |
| SO | WINDOWS SERVER 2019 |
| IP-01 | 192.168.2.4 |
| IP-02 | 172.16.2.4 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.2.4|
| DNS-02 | 192.168.0.3|
| RAM | 2GB |
| vCPU | 1 |
| CORES | 2 |
| DISK | 16GB |
| FQDN | ad02.dr.labvsp.local |
| AMBIENTE | DR |
| HOST | esxi01.dr.labvsp.local |
| DATASTORE | LUN-iSCSI-01 |

</center>

</details>

---

</details>

---

## VEEAM
Infraestrutura do ambiente de backup.

<details>
<summary>VMs</summary>
O ambiente é composto por 4 vms, sendo:

* 1 Windows Server 2019 - Servidor principal;
* 4 Ubuntu Server  20.04 LTS - Proxys do Veeam.


<details>
<summary>SRV-VEEAM</summary>

<center>

| HOSTNAME | SRV-VEEAM |
| :---: | :---: |
| USUÁRIO | Administrator |
| SENHA | zaq1@WSX |
| SO | WINDOWS SERVER 2019 |
| IP | 192.168.0.10 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.0.2|
| RAM | 8GB |
| vCPU | 1 |
| CORES | 4 |
| DISK-01 | 64GB |
| DISK-02 | 256GB |
| FQDN | srv-veeam.labvsp.local |

</center>

</details>

---

<details>
<summary>PROXY01</summary>

<center>

| HOSTNAME | PROXY01 |
| :---: | :---: |
| USUÁRIO | administrator |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | UBUNTU SERVER 20.04 LTS |
| IP | 192.168.0.11 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.0.2|
| RAM | 4GB |
| vCPU | 1 |
| CORES | 2 |
| DISK | 16GB |
| FQDN | proxy01.labvsp.local |

</center>

</details>

---

<details>
<summary>PROXY02</summary>

<center>

| HOSTNAME | PROXY02 |
| :---: | :---: |
| USUÁRIO | administrator |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | UBUNTU SERVER 20.04 LTS |
| IP | 192.168.0.12 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.0.2|
| RAM | 4GB |
| vCPU | 1 |
| CORES | 2 |
| DISK | 16GB |
| FQDN | proxy02.labvsp.local |

</center>

</details>

---

<details>
<summary>PROXY-PROD</summary>

<center>

| HOSTNAME | PROXY-PROD |
| :---: | :---: |
| USUÁRIO | administrator |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | UBUNTU SERVER 20.04 LTS |
| IP | 192.168.1.30 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.0.2|
| RAM | 4GB |
| vCPU | 1 |
| CORES | 2 |
| DISK | 16GB |
| FQDN | proxy.prod.labvsp.local |
| AMBIENTE | PROD |
| HOST | esxi03.prod.labvsp.local |
| DATASTORE | LUN-iSCSI-02 |

</center>

</details>

---

<details>
<summary>PROXY-DR</summary>

<center>

| HOSTNAME | PROXY-DR |
| :---: | :---: |
| USUÁRIO | administrator |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | UBUNTU SERVER 20.04 LTS |
| IP | 192.168.2.30 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.0.2|
| RAM | 4GB |
| vCPU | 1 |
| CORES | 2 |
| DISK | 16GB |
| FQDN | proxy.dr.labvsp.local |
| AMBIENTE | DR |
| HOST | esxi02.dr.labvsp.local |
| DATASTORE | LUN-iSCSI-02 |

</center>

</details>

---

</details>

---

## PROD
Infraestrutura do ambiente de Produção.

<details>
<summary>VMs</summary>
O ambiente é composto por 5 vms, sendo:

* 3 vSPHERE ESXi 6.5 - Hosts ESXi;
* 1 vCenter Server 6.5 - Gerenciador dos ambiente;
* 1 VSA 2014 - Storage da HP.

---

<details>
<summary>OVERVIEW</summary>

<center>

| IP | FQDN |
| :---: | :---: |
| 192.168.1.10 | vcenter.prod.labvsp.local |
| 192.168.1.11 | esxi01.prod.labvsp.local |
| 192.168.1.12 | esxi02.prod.labvsp.local |
| 192.168.1.13 | esxi03.prod.labvsp.local |
| 192.168.1.21 | vsa.prod.labvsp.local |

</center>

</details>

---

<details>
<summary>ESXi01</summary>

<center>

| HOSTNAME | esxi01 |
| :---: | :---: |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | vSPHERE ESXi 6.5 |
| IP | 192.168.1.11 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.1.4|
| SUFIXO DNS | prod.labvsp.local |
| RAM | 16GB |
| vCPU | 2 |
| CORES | 3 |
| DISK | 10GB |
| ADAPTADORES DE REDE | 8 |
| iSCSI | iqn.1998-01.com.vmware:esxi01-2b374409 |
| FQDN | esxi01.prod.labvsp.local |

</center>

### Configuração dos Virutal Swithces:
* **vSwitch0**:
    * Adaptadores:
        * vmnic 0;
        * vmnic 1.
    * Networking:
        * **Management Network**:
            * Tipo: VMKernel;
            * IP: 192.168.1.11;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1.
        * **vMotion**:
            * Tipo: VMKernel;
            * IP: 192.168.111.1;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1;
* **vSwitch1**:
    * Adaptadores:
        * vmnic 2;
        * vmnic 3.
    * Networking:
        * **PROD**:
            * Tipo: VM Port Group;
            * Adaptadores:
                * vmnic 2;
                * vmnic 3.
* **vSwitch2**:
    * Adaptadores:
        * vmnic 4;
        * vmnic 5.
    * Networking:
        * **FT**:
            * Tipo: VMKernel;
            * IP: 192.168.121.1
            * Adaptadores:
                * vmnic 4;
                * vmnic 5.
* **vSwitch3**:
    * Adaptadores:
        * vmnic 6;
        * vmnic 7.
    * Networking:
        * **iSCSI-PORT-A**:
            * Tipo: VMKernel;
            * IP: 172.16.111.1
            * Adaptadores:
                * vmnic 6.
        * **iSCSI-PORT-B**:
            * Tipo: VMKernel;
            * IP: 172.16.111.2;
            * Adaptadores:
                * vmnic 7;

</details>

---

<details>
<summary>ESXi02</summary>

<center>

| HOSTNAME | esxi02 |
| :---: | :---: |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | vSPHERE ESXi 6.5 |
| IP | 192.168.1.12 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.1.4|
| SUFIXO DNS | prod.labvsp.local |
| RAM | 16GB |
| vCPU | 2 |
| CORES | 3 |
| DISK | 10GB |
| ADAPTADORES DE REDE | 8 |
| iSCSI | iqn.1998-01.com.vmware:esxi02-6cb32662 |
| FQDN | esxi02.prod.labvsp.local |

</center>

### Configuração dos Virutal Swithces:
* **vSwitch0**:
    * Adaptadores:
        * vmnic 0;
        * vmnic 1.
    * Networking:
        * **Management Network**:
            * Tipo: VMKernel;
            * IP: 192.168.1.12;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1.
        * **vMotion**:
            * Tipo: VMKernel;
            * IP: 192.168.112.1;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1;
* **vSwitch1**:
    * Adaptadores:
        * vmnic 2;
        * vmnic 3.
    * Networking:
        * **PROD**:
            * Tipo: VM Port Group;
            * Adaptadores:
                * vmnic 2;
                * vmnic 3.
* **vSwitch2**:
    * Adaptadores:
        * vmnic 4;
        * vmnic 5.
    * Networking:
        * **FT**:
            * Tipo: VMKernel;
            * IP: 192.168.122.1
            * Adaptadores:
                * vmnic 4;
                * vmnic 5.
* **vSwitch3**:
    * Adaptadores:
        * vmnic 6;
        * vmnic 7.
    * Networking:
        * **iSCSI-PORT-A**:
            * Tipo: VMKernel;
            * IP: 172.16.112.1
            * Adaptadores:
                * vmnic 6.
        * **iSCSI-PORT-B**:
            * Tipo: VMKernel;
            * IP: 172.16.112.2;
            * Adaptadores:
                * vmnic 7;

</details>

---

<details>
<summary>ESXi03</summary>

<center>

| HOSTNAME | esxi03 |
| :---: | :---: |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | vSPHERE ESXi 6.5 |
| IP | 192.168.1.13 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.1.4|
| SUFIXO DNS | prod.labvsp.local |
| RAM | 16GB |
| vCPU | 2 |
| CORES | 3 |
| DISK | 10GB |
| ADAPTADORES DE REDE | 8 |
| iSCSI | iqn.1998-01.com.vmware:esxi03-5ae6058b |
| FQDN | esxi03.prod.labvsp.local |

</center>

### Configuração dos Virutal Swithces:
* **vSwitch0**:
    * Adaptadores:
        * vmnic 0;
        * vmnic 1.
    * Networking:
        * **Management Network**:
            * Tipo: VMKernel;
            * IP: 192.168.1.13;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1.
        * **vMotion**:
            * Tipo: VMKernel;
            * IP: 192.168.113.1;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1;
* **vSwitch1**:
    * Adaptadores:
        * vmnic 2;
        * vmnic 3.
    * Networking:
        * **PROD**:
            * Tipo: VM Port Group;
            * Adaptadores:
                * vmnic 2;
                * vmnic 3.
* **vSwitch2**:
    * Adaptadores:
        * vmnic 4;
        * vmnic 5.
    * Networking:
        * **FT**:
            * Tipo: VMKernel;
            * IP: 192.168.131.1
            * Adaptadores:
                * vmnic 4;
                * vmnic 5.
* **vSwitch3**:
    * Adaptadores:
        * vmnic 6;
        * vmnic 7.
    * Networking:
        * **iSCSI-PORT-A**:
            * Tipo: VMKernel;
            * IP: 172.16.113.1
            * Adaptadores:
                * vmnic 6.
        * **iSCSI-PORT-B**:
            * Tipo: VMKernel;
            * IP: 172.16.113.2;
            * Adaptadores:
                * vmnic 7;

</details>

---

<details>
<summary>vCenter</summary>

<center>

| HOSTNAME | vcenter |
| :---: | :---: |
| USUÁRIO | root |
| USUÁRIO | administrator@vsphere.local |
| SENHA | zaq1@WSX |
| SO | vCenter Server 6.5 |
| IP | 192.168.1.10 |
| MÁSCARA | 16 |
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.1.4|
| SUFIXO DNS | prod.labvsp.local |
| RAM | 10GB |
| vCPU | 2 |
| CORES | 1 |
| DISK | 250GB |
| ADAPTADORES DE REDE | 1 |
| FQDN | vcenter.prod.labvsp.local |

</center>

</details>

---

<details>
<summary>VSA</summary>

<center>

| HOSTNAME | vsa |
| :---: | :---: |
| USUÁRIO | admin |
| SENHA | zaq1@WSX |
| SO | VSA 2014 |
| IP | 192.168.1.21 |
| IP | 172.16.1.21 |
| VIP | 172.16.1.20 |
| MÁSCARA | 255.255.0.0 |
| GATEWAY | 192.168.0.2 |
| SUFIXO DNS | prod.labvsp.local |
| RAM | 4GB |
| vCPU | 1 |
| CORES | 2 |
| DISK-01 | 32GB |
| DISK-01 | 520GB |
| ADAPTADORES DE REDE | 2 |
| FQDN | vsa.prod.labvsp.local |
| VIP FQDN | vip.prod.labvsp.local |

</center>

</details>

---

</details>

---

## DR
Infraestrutura do ambiente de DR.

<details>
<summary>VMs</summary>
O ambiente é composto por 4 vms, sendo:

* 2 vSPHERE ESXi 6.5 - Hosts ESXi;
* 1 vCenter Server 6.5 - Gerenciador dos ambiente;
* 1 VSA 2014 - Storage da HP.

---

<details>
<summary>OVERVIEW</summary>

<center>

| IP | FQDN |
| :---: | :---: |
| 192.168.2.10 | vcenter.dr.labvsp.local |
| 192.168.2.11 | esxi01.dr.labvsp.local |
| 192.168.2.12 | esxi02.dr.labvsp.local |
| 192.168.2.21 | vsa.dr.labvsp.local |

</center>

</details>

---

<details>
<summary>ESXi01</summary>

<center>

| HOSTNAME | esxi01 |
| :---: | :---: |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | vSPHERE ESXi 6.5 |
| IP | 192.168.2.11 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.2.4|
| SUFIXO DNS | dr.labvsp.local |
| RAM | 16GB |
| vCPU | 2 |
| CORES | 3 |
| DISK | 10GB |
| ADAPTADORES DE REDE | 8 |
| iSCSI | ?? |
| FQDN | esxi01.dr.labvsp.local |

</center>

### Configuração dos Virutal Swithces:
* **vSwitch0**:
    * Adaptadores:
        * vmnic 0;
        * vmnic 1.
    * Networking:
        * **Management Network**:
            * Tipo: VMKernel;
            * IP: 192.168.2.11;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1.
        * **vMotion**:
            * Tipo: VMKernel;
            * IP: 192.168.211.2;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1;
* **vSwitch1**:
    * Adaptadores:
        * vmnic 2;
        * vmnic 3.
    * Networking:
        * **PROD**:
            * Tipo: VM Port Group;
            * Adaptadores:
                * vmnic 2;
                * vmnic 3.
* **vSwitch2**:
    * Adaptadores:
        * vmnic 4;
        * vmnic 5.
    * Networking:
        * **FT**:
            * Tipo: VMKernel;
            * IP: 192.168.221.2
            * Adaptadores:
                * vmnic 4;
                * vmnic 5.
* **vSwitch3**:
    * Adaptadores:
        * vmnic 6;
        * vmnic 7.
    * Networking:
        * **iSCSI-PORT-A**:
            * Tipo: VMKernel;
            * IP: 172.16.211.1
            * Adaptadores:
                * vmnic 6.
        * **iSCSI-PORT-B**:
            * Tipo: VMKernel;
            * IP: 172.16.211.2;
            * Adaptadores:
                * vmnic 7;

</details>

---

<details>
<summary>ESXi02</summary>

<center>

| HOSTNAME | esxi02 |
| :---: | :---: |
| USUÁRIO | root |
| SENHA | zaq1@WSX |
| SO | vSPHERE ESXi 6.5 |
| IP | 192.168.2.12 |
| MÁSCARA | 255.255.0.0|
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.2.4|
| SUFIXO DNS | dr.labvsp.local |
| RAM | 16GB |
| vCPU | 2 |
| CORES | 3 |
| DISK | 10GB |
| ADAPTADORES DE REDE | 8 |
| iSCSI | ?? |
| FQDN | esxi02.dr.labvsp.local |

</center>

### Configuração dos Virutal Swithces:
* **vSwitch0**:
    * Adaptadores:
        * vmnic 0;
        * vmnic 1.
    * Networking:
        * **Management Network**:
            * Tipo: VMKernel;
            * IP: 192.168.1.12;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1.
        * **vMotion**:
            * Tipo: VMKernel;
            * IP: 192.168.212.2;
            * Adaptadores:
                * vmnic 0;
                * vmnic 1;
* **vSwitch1**:
    * Adaptadores:
        * vmnic 2;
        * vmnic 3.
    * Networking:
        * **PROD**:
            * Tipo: VM Port Group;
            * Adaptadores:
                * vmnic 2;
                * vmnic 3.
* **vSwitch2**:
    * Adaptadores:
        * vmnic 4;
        * vmnic 5.
    * Networking:
        * **FT**:
            * Tipo: VMKernel;
            * IP: 192.168.222.2
            * Adaptadores:
                * vmnic 4;
                * vmnic 5.
* **vSwitch3**:
    * Adaptadores:
        * vmnic 6;
        * vmnic 7.
    * Networking:
        * **iSCSI-PORT-A**:
            * Tipo: VMKernel;
            * IP: 172.16.212.1
            * Adaptadores:
                * vmnic 6.
        * **iSCSI-PORT-B**:
            * Tipo: VMKernel;
            * IP: 172.16.212.2;
            * Adaptadores:
                * vmnic 7;

</details>

---

<details>
<summary>vCenter</summary>

<center>

| HOSTNAME | vcenter |
| :---: | :---: |
| USUÁRIO | root |
| USUÁRIO | administrator@vsphere.local |
| SENHA | zaq1@WSX |
| SO | vCenter Server 6.5 |
| IP | 192.168.2.10 |
| MÁSCARA | 16 |
| GATEWAY | 192.168.0.2 |
| DNS-01 | 192.168.0.3|
| DNS-02 | 192.168.2.4|
| SUFIXO DNS | dr.labvsp.local |
| RAM | 10GB |
| vCPU | 2 |
| CORES | 1 |
| DISK | 250GB |
| ADAPTADORES DE REDE | 1 |
| FQDN | vcenter.dr.labvsp.local |

</center>

</details>

---

<details>
<summary>VSA</summary>

<center>

| HOSTNAME | vsa |
| :---: | :---: |
| USUÁRIO | admin |
| SENHA | zaq1@WSX |
| SO | VSA 2014 |
| IP | 192.168.2.21 |
| IP | 172.16.2.21 |
| VIP | 172.16.2.20 |
| MÁSCARA | 255.255.0.0 |
| GATEWAY | 192.168.0.2 |
| SUFIXO DNS | dr.labvsp.local |
| RAM | 4GB |
| vCPU | 1 |
| CORES | 2 |
| DISK-01 | 32GB |
| DISK-01 | 520GB |
| ADAPTADORES DE REDE | 2 |
| FQDN | vsa.dr.labvsp.local |
| VIP FQDN | vip.dr.labvsp.local |

</center>

</details>

---

</details>

---
