# azure-site-recovery
Azure Workshop "Valis v0.3"

---------------
Templates
---------------
```
az deployment create --template-uri https://raw.githubusercontent.com/MadarsSmits/azure-site-recovery/master/rg.json --verbose --location westeurope
```
```
az group deployment create --template-uri https://raw.githubusercontent.com/MadarsSmits/azure-site-recovery/master/template-BSR.json --verbose --resource-group valis3-BSR --no-wait
```
```
az group deployment create --template-uri https://raw.githubusercontent.com/MadarsSmits/azure-site-recovery/master/template-VMs.json --verbose --resource-group valis3-VMs --no-wait
```
```
az group deployment create --template-uri https://raw.githubusercontent.com/MadarsSmits/azure-site-recovery/master/template-Failover.json --verbose --resource-group valis3-VMs-Failover --no-wait
```

__valis3-BSR:__
- valis3-BSR
- valis3-VNET
- pc47ofbueyttustorage

__valis3-VMs__
- HyperV-NIC
- HyperV-PublicIP
- HyperV-VM
- HyperV-VM_OsDisk
- SQL-NIC
- SQL-PublicIP
- SQL-VM
- SQL-VM_disk2
- SQL-VM_OsDisk
- VMs-NSG
- VMs-VNET
- w5uxvybrmvtxmsqlserver
- w5uxvybrmvtxmsqlserver/simpledatabase

Manual
- Run "Azure_NestedHyper-V_Script.ps1" secound time
- Join Valis Storage Account with SMB and copy both VMs
- Import both copied VMs into Hyper-V Manager

__valis3-VMs-Failover__
- VMs-BSR-Failover
- VMs-VNET-Failover