DTS configuration files

# conf/crbs.cfg  --------
```
#DUT crbs Configuration
#[DUT IP]
#  dut_ip: DUT ip address
#  dut_user: Login DUT username
#  dut_passwd: Login DUT password
#  os: operation system type linux or freebsd
#  tester_ip: Tester ip address
#  tester_passwd: Tester password
#  ixia_group: IXIA group name
#  channels: Board channel number
#  bypass_core0: Whether by pass core0
[10.101.2.118]
dut_ip=10.101.2.118
dut_user=root
dut_passwd=linaro
os=linux
tester_ip=10.101.3.56
tester_passwd=linaro
ixia_group=
channels=4
bypass_core0=True
```



# conf/ports.cfg  ---------
```
# DUT Port Configuration
# [DUT IP]
# ports=
#     pci=Pci BDF,intf=Kernel interface;
#     pci=Pci BDF,mac=Mac address,peer=Tester Pci BDF,numa=Port Numa
#     pci=Pci BDF,peer=IXIA:card.port
#     pci=Pci BDF,peer=Tester Pci BDF,tp_ip=$(IP),tp_path=$({PERL_PATH);
#     pci=Pci BDF,peer=Tester Pci BDF,sec_port=yes,first_port=Pci BDF;
# [VM NAME] virtual machine name; This section is for virutal scenario
# ports =
#     dev_idx=device index of ports info, peer=Tester Pci BDF
[10.101.2.118]
ports =
    pci=0002:01:00.2,peer=0002:01:00.2;
    pci=0002:01:00.3,peer=0002:01:00.3;
```




# execution.cfg  ---------
```
[Execution1]
crbs=10.101.2.118
drivername=vfio-pci
test_suites=
    hello_world,
targets=
    arm64-armv8a-linuxapp-gcc
parameters=nic_type=cfg:func=true
```


