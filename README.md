# Linux-HA-Config
Linux HA Reminder

---

## Git Large File Storage (LFS)
[LFS](https://git-lfs.com/)

## Line of Services
```
********************************业务范围********************************

一、 集团数据中心机房（EDC）运维/管理
1，物理环境&硬件设施
(1) ，主机房：存储阵列、服务器群、网络负载均衡、防火墙、路由器、交换机、SWG&WAF&IDS/IPS&SIP&VPN等应用的硬件设备、机柜配线（供电、FTP/STP/UTP、FC/SC）、精密空调/新风系统、环境监控（视频监控、门禁、烟感、温感、漏水检测、气体灭火系统-七氟丙烷等）。
(2) ，基本工作房间：办公室、服务窗口、待交付主机/显示器/键盘/鼠标等。
(3) ，第一类辅助间：维修室、仪器室、备件库、磁带库、备用磁盘、防静电手环、光模块/跳线、STP/UTP成品线/五类线/水晶头、移动存储（移动硬盘、U盘）、储备主机/显示器等。
(4) ，第二类辅助间：低压配电、UPS电源和蓄电池、备用电池。
(5) ，第三类辅助间：待报废的设备、未分类的设备、储备耗材（键盘、鼠标等）。

2，操作系统&基础应用
(1) ，标准操作系统：Windows Server 2019/2022，Redhat Enterprise Linux，Rocky Linux，CentOS Linux 7（将弃用），Debian GNU/Linux，Ubuntu Server，SUSE Linux Enterprise Server (SLES)。
(2) ，基础设施应用：VMware vSphere，H3C UIS，Keepalived-Nginx Cluster，Patroni (HA) PostgreSQL Cluster，MySQL NDB Cluster，MariaDB Galera Cluster，MS SQL Server，Microsoft Active Directory(PDC, SDC, BDC, RDC, SMB, WSUS)，DNS/DHCP Server，GitLab，Jenkins，Nexus，Harbor，Docker/Podman，MinIO，Zabbix，ZenTaoPMS，MS KMS等。


二、 集团网络运行中心（NOC）运维/管理
1，数通设备&路由交换
(1) ，Business/Services <-> VLAN <-> IP_Address Mapping Plan/Rules。
(2) ，机柜位图、网络物理拓扑图、网络逻辑链路图、静态路由表、物理链路接口（Port Map）表。

2，安全设备&安全策略
(1) ，安全感知平台（SIP）：安全事件/风险处置。
(2) ，网络防火墙、SWG&WAF&IDS/IPS：参考https://support.huawei.com/enterprise/zh/doc/EDOC1100164709文档，须遵循的原则：a，建立完善的安全策略管理流程；b，使用安全区域划分网络；c，遵循最小授权原则；d，顺序很重要，先精确后宽泛，先常用后少用；e，出入方向的流量都要识别和控制；f，谨慎选择变更时机，适时启用策略备份加速；g，定期审计和优化安全策略。


三、 集团安全运营中心（SOC）运维/管理
1，安全设施&安保政策
(1) ，机房环境安全监控（视频监控、门禁、烟感、温感、漏水检测、气体灭火系统-七氟丙烷等），网络物理链路（光缆、光纤、五类线等）综合布线安全，物理设备（硬件服务器、UPS冗余电源）安全巡检、排障。
(2) ，信息安全保密政策、软件/文档密级管理、信息安全意识培训、应对外部网络攻击和内部泄密风险的措施等。

2，安全风险&安全事件
(1) ，安全感知平台（SIP）：安全事件/风险处置，解除误报，完善防火墙、IDS/IPS等信息安全设备配置，修补安全漏洞形成安全闭环。
(2) ，处理已经报告或监控到的安全事件，完善安全响应机制，提高安全事件回溯能力，建立高可用、快恢复、零损失的安全管理框架。


四、 集团全员桌面终端（HelpDesk）规程/事件
1，终端标准&文件备份&事件处置
(1) ，标准操作系统：Windows 10 Professional、Windows 11 Professional、UOS Linux、MacOS等桌面系统。
(2) ，标准软件清单：a，基础软件（WPS、MS Office、MS Visio、MS Project、Foxmail、企业微信、腾讯会议、Google Chrome、Mozilla Firefox、Everything、Flameshot、Captura、ToDesk、Q-Dir、7-Zip、微信等）；b，安全软件（Cisco ISE、IP-Guard等）；c，专业软件（Autodesk AutoCAD、Adobe Acrobat DC、JetBrains IntelliJ IDEA、JetBrains WebStorm、JetBrains PyCharm等）；d，业务软件（Weaver OA、SAP GUI、yonyou UClient等）。

2，账号管理（AD，尚未实现）&文件访问权限控制
(1) ，AD/LDAP组织架构更新、用户/组账号管理、网络驱动器（个人盘 I:\ & 共享盘 S:\）。
(2) ，Windows Server SMB/CIFS 文件访问权限管理、NAS集成AD账号及其权限管理/安全审计、文件备份/硬盘低格。

3，桌面运维 KB、SOP、Contracts 等文档更新/存档
(1) ，桌面运维 KB 分类：操作系统类、网络故障类、应用软件类等。
(2) ，标准操作规程 SOP（LoS）：员工入职/离职、转岗变更权限、信息安全培训（包括入职培训）、信息安全检查（季度、年度）等。
(3) ，合同/备案/审批/整改方案等文件管理：ISP互联网接入合同、机房重要系统维保合同、网络/安全/服务器软硬件优化方案、SRE 运维文档（机柜图、网络物理/逻辑拓扑图、硬件设备清单、无线AP点位图、有线接入点位图、业务-VLAN-IP地址计划/映射表、重要基础服务如数据库登记表、应用系统登记表等）、其他管理文档。


五、 集团数字化中心各应用系统事件处置/升级（SLA）
1，应用系统业务相关事件预处理与工单转移/升级
(1) ，应用系统清单：DCS、SIS、安全生产信息化管理平台（对接EHS/HSE）、yonyou NC、Weaver OA、CRM、SRM、HRM、Enterprise Mail、SAC、企业微信、Cisco ISE准入、IP-Guard加密、SIP态势感知、SAP GUI、SAP-GR合并报表、SAP-FICO、SAP-SD、SAP-MM、SAP-PM、SAP-PP、SAP-QM、SAP-MDG、二维码溯源系统、无人值守地磅系统、金税系统、实时数据库、RPA机器人、智能仓库、档案集成系统、PMS项目管理系统等。
(2) ，根据 SLA 处理应用系统事件，升级事件到相应系统的后端负责人，跟踪并闭环（关闭）用户事件工单。对新问题，在处理完毕后，及时更新知识库（KB），形成参考文档，以备今后使用（事件触发背景、分析思路、解决方案）。

2，B/S、C/S 架构软件基础服务维护（客户端、服务端）
(1) ，按需（用户工单、警报时间）调整基础服务资源配置（计算资源、存储资源、网络资源），保障基础服务（如数据库集群）的高可用和稳定性，保障数据备份的有效性和安全性。
(2) ，在测试环境、预发布环境、生产环境部署应用系统，维护 DevOps 基础设施，如 GitLab，Jenkins，Nexus，Harbor，MinIO，Zabbix，完善 网络/系统 监控机制（通过 SIP、H3C IMC、Zabbix 或 Cacti、Nagios、Prometheus、MRTG、PRTG等）和监测告警方式。


六、 集团IT资产全生命周期管理（NIM, Network Inventory Management）
1，终端设备（笔记本、迷你机、塔式机、图形工作站、独立显示器）及外围设备/耗材资产管理
(1) ，制定资产标签格式标准，维护固定资产台账，整理供应商和维保资料。
(2) ，制定采购计划、维保需求、报废标准等，定期盘点固定资产（季度或年度）。

2，网络设备（数通设备、安全设备）及外围设备/耗材资产管理
(1) ，制定资产标签格式标准，维护固定资产台账，整理供应商和维保资料。
(2) ，制定采购计划、维保需求、报废标准等，定期盘点固定资产（季度或年度）。

3，裸金属服务器、超融合虚拟化（PVE、UIS、vSphere）、存储网络（vSAN/iSCSI）、文件存储（NFS/SMB）及外围设备/耗材资产管理
(1) ，制定资产标签格式标准，维护固定资产台账，整理供应商和维保资料。
(2) ，制定采购计划、维保需求、报废标准等，定期盘点固定资产（季度或年度）。


```

---

## MySQLD Lower Case Table Names
sudo systemctl stop mysql.service  
sudo mv /var/lib/mysql /var/lib/mysql~  
sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf  
sudo mysqld --initialize --user=mysql --lower-case-table-names=1  
sudo systemctl start mysql.service  
mysql -uroot -hlocalhost -p$(sudo grep -- 'A temporary password is generated' /var/log/mysql/error.log | awk '{print $NF}')  
  mysql> 
```
        -- BOS
        -- User: `isa`@`localhost`
        SELECT User,Host FROM mysql.user;
        INSTALL PLUGIN auth_socket SONAME 'auth_socket.so';
        --
        SHOW CREATE USER `root`@`localhost`;
        CREATE USER `isa`@`localhost` IDENTIFIED WITH 'auth_socket' REQUIRE NONE PASSWORD EXPIRE DEFAULT ACCOUNT UNLOCK PASSWORD HISTORY DEFAULT PASSWORD REUSE INTERVAL DEFAULT PASSWORD REQUIRE CURRENT DEFAULT;
        SHOW CREATE USER `isa`@`localhost`;
        --
        SHOW GRANTS FOR `root`@`localhost`;
        GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, RELOAD, SHUTDOWN, PROCESS, FILE, REFERENCES, INDEX, ALTER, SHOW DATABASES, SUPER, CREATE TEMPORARY TABLES, LOCK TABLES, EXECUTE, REPLICATION SLAVE, REPLICATION CLIENT, CREATE VIEW, SHOW VIEW, CREATE ROUTINE, ALTER ROUTINE, CREATE USER, EVENT, TRIGGER, CREATE TABLESPACE, CREATE ROLE, DROP ROLE ON *.* TO `isa`@`localhost` WITH GRANT OPTION;
        GRANT APPLICATION_PASSWORD_ADMIN,AUDIT_ABORT_EXEMPT,AUDIT_ADMIN,AUTHENTICATION_POLICY_ADMIN,BACKUP_ADMIN,BINLOG_ADMIN,BINLOG_ENCRYPTION_ADMIN,CLONE_ADMIN,CONNECTION_ADMIN,ENCRYPTION_KEY_ADMIN,FIREWALL_EXEMPT,FLUSH_OPTIMIZER_COSTS,FLUSH_STATUS,FLUSH_TABLES,FLUSH_USER_RESOURCES,GROUP_REPLICATION_ADMIN,GROUP_REPLICATION_STREAM,INNODB_REDO_LOG_ARCHIVE,INNODB_REDO_LOG_ENABLE,PASSWORDLESS_USER_ADMIN,PERSIST_RO_VARIABLES_ADMIN,REPLICATION_APPLIER,REPLICATION_SLAVE_ADMIN,RESOURCE_GROUP_ADMIN,RESOURCE_GROUP_USER,ROLE_ADMIN,SENSITIVE_VARIABLES_OBSERVER,SERVICE_CONNECTION_ADMIN,SESSION_VARIABLES_ADMIN,SET_USER_ID,SHOW_ROUTINE,SYSTEM_USER,SYSTEM_VARIABLES_ADMIN,TABLE_ENCRYPTION_ADMIN,TELEMETRY_LOG_ADMIN,XA_RECOVER_ADMIN ON *.* TO `isa`@`localhost` WITH GRANT OPTION;
        GRANT PROXY ON ``@`` TO `isa`@`localhost` WITH GRANT OPTION;
        SHOW GRANTS FOR `isa`@`localhost`;
        -- ==
        -- User: `api`@`%`
        CREATE USER `api`@`%` IDENTIFIED WITH 'mysql_native_password' BY '_api@MySQL' REQUIRE NONE PASSWORD EXPIRE DEFAULT ACCOUNT UNLOCK PASSWORD HISTORY DEFAULT PASSWORD REUSE INTERVAL DEFAULT PASSWORD REQUIRE CURRENT DEFAULT;
        SHOW CREATE USER `api`@`%`;
        --
        GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP, RELOAD, SHUTDOWN, PROCESS, FILE, REFERENCES, INDEX, ALTER, SHOW DATABASES, SUPER, CREATE TEMPORARY TABLES, LOCK TABLES, EXECUTE, REPLICATION SLAVE, REPLICATION CLIENT, CREATE VIEW, SHOW VIEW, CREATE ROUTINE, ALTER ROUTINE, CREATE USER, EVENT, TRIGGER, CREATE TABLESPACE, CREATE ROLE, DROP ROLE ON *.* TO `api`@`%` WITH GRANT OPTION;
        SHOW GRANTS FOR `api`@`%`;
        -- ==
        -- Database: `data`
        CREATE DATABASE `data` /*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci */ /*!80016 DEFAULT ENCRYPTION='N' */;
        SHOW CREATE DATABASE `data`;
        -- EOS
```

---

## vSAN-Cluster

### Backup(Datastore & System)
- Veeam-Linux-Backup_Server
- Veeam-Linux-Immutable_Storage

### Penetration Testing Environment

#### Penetration Testing OS
- PTOS-STAFFID-V01

### Prod Env GNU/Linux Servers

#### DevOps & ITIL/ITSM

##### CI/CD & PMS
- CD-Jenkins

##### NOC/SOC Bastion Host
- Bastion
- JumpServer

#### Information System Infrastructure

##### Keepalived-MariaDB-Clusters

###### MariaDB-Galera-Cluster1
- MariaDB-Galera-Cluster1-3_0
- MariaDB-Galera-Cluster1-3_1
- MariaDB-Galera-Cluster1-3_2

##### Keepalived-MinIO-3
- Keepalived-MinIO-3_0
- Keepalived-MinIO-3_1
- Keepalived-MinIO-3_2

##### Keepalived-MySQL-Clusters

###### MySQL-NDB-Cluster1
- MySQL-NDB-Cluster1-3_0
- MySQL-NDB-Cluster1-3_1
- MySQL-NDB-Cluster1-3_2

##### Keepalived-Nginx-3
- Keepalived-Nginx-3_0
- Keepalived-Nginx-3_1
- Keepalived-Nginx-3_2

##### Nginx-Standalone-Servers
- Nginx-Standalone-Global
- Nginx-Standalone-Global-KeptBack

#### Application HA Servers
- Vendor-App-HA-Active
- Vendor-App-HA-Passive
- Vendor-App-HA-Witness

#### Networks & Servers Monitoring

##### Native-Zabbix-HA-Cluster
- Native-Zabbix-HA-3_0
- Native-Zabbix-HA-3_1
- Native-Zabbix-HA-3_2

#### Other Servers
- App-Components-Main

### Prod Env MS/Windows Servers

#### DevOps & ITIL/ITSM

##### CI/CD & PMS
- App-Components-Main

##### NOC/SOC Bastion Host
- AppServer0
- AppServer1
- AppServer2

#### Information System Infrastructure

##### DNS/DHCP & KRB5/LDAP & MS/AD

###### DNS/DHCP Servers
- DNS_DHCP-Primary
- DNS_DHCP-Secondary

###### KRB5/LDAP Servers
- KRB5_LDAP-Primary
- KRB5_LDAP-Secondary

###### MS Active Directory
- MSAD-PDC
- MSAD-SDC
- MSAD-BDC
- MSAD-RDC
- MSAD-SMB
- MSAD-WSUS

#### RPA - Robotic Process Automation

##### RPA - ShadowBot
- ShadowBot(01)
- ShadowBot(02)

##### RPA - UiPath
- UiPath(01)
- UiPath(02)

### Test Env GNU/Linux Servers

### Test Env MS/Windows Servers

### VMware vCenter Server8 HA-Cluster
- VMware vCenter Server8-Active
- VMware vCenter Server8-Passive
- VMware vCenter Server8-Witness

---

## Shell History

### Patroni : Setting up a highly available PostgreSQL Cluster
```
patroni -h
patronictl --help
patronictl -c /etc/patroni/znode{0,1,2}.yml list
patronictl -c /etc/patroni/znode{0,1,2}.yml reinit 15/zabbix
patronictl -c /etc/patroni/znode{0,1,2}.yml reinit 15/zabbix znode{0,1,2}
sudo vim /etc/patroni/dcs.yml
sudo pg_createconfig_patroni 15 zabbix
sudo -iu postgres -g postgres /usr/lib/postgresql/15/bin/pg_ctl status -D /var/lib/postgresql/15/zabbix
sudo -iu postgres -g postgres patroni --generate-config --dsn "user=postgres $(patronictl -c /etc/patroni/znode{0,1,2}.yml dsn) password=postgres"
sudo -iu postgres -g postgres /usr/lib/postgresql/15/bin/pg_basebackup --pgdata=/var/lib/postgresql/15/zabbix -X stream "--dbname=dbname=postgres user=postgres host=10.16.5.236 port=5433 password=postgres"
```

### File Encoding Converting
```
iconv -f UTF-8 -t GB18030 -o file.gb18030 file.utf8
vim --cmd 'set fileencodings-=latin1' --cmd 'set fileencodings+=cp936' -c 'set fileencoding=cp936' -c 'wq' file.utf8

iconv -f GB18030 -t UTF-8 -o file.utf8 file.gb18030
vim --cmd 'set fileencodings-=latin1' --cmd 'set fileencodings+=cp936' -c 'set fileencoding=utf-8' -c 'wq' file.gb18030
```

### Nginx -- Test configuration
```
sudo nginx -t
sudo systemctl reload-or-restart nginx.service
```

### TAR GZ GPG Encryption/Decryption
```
tar -cpzvf - misc | gpg --symmetric --cipher-algo AES256 -o misc.tar.gz.gpg
gpg -d --batch --yes --passphrase 'GuessWhat' misc.tar.gz.gpg | tar -zvxf -
```

### Print Unicode Characters
```
for i in {0..255}; do printf "%x: $(unicode -d $((0x2500+$i)) | awk 'NR==3{print $1}')\n\n" $i; done
```

