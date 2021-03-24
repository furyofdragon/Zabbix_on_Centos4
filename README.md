# Zabbix agent on Centos 4

**Problem**: officionally zabbix agent couldn't run on Centos 4 (because of old glibc version).

1. Download src

    ``wget http://sourceforge.net/projects/zabbix/files/ZABBIX%20Latest%20Stable/2.2.16/zabbix-2.2.16.tar.gz/download --no-check-certificate``  
    or  
    ``wget http://sourceforge.net/projects/zabbix/files/ZABBIX%20Latest%20Stable/2.2.16/zabbix-2.2.16.tar.gz/download``  

2. ``tar -zxvf zabbix-2.2.16.tar.gz``

3. ``cd zabbix-2.2.16``

4. ``./configure --enable-agent --prefix=your_prefix``

5. ``make``

6. ``make install``

7. edit configs in your_prefix/etc

8. your_prefix/sbin/zabbix_agentd

9. Create user account (if needed)  
``groupadd zabbix``  
``useradd -g zabbix zabbix``

10. For autostart  
put zabbix-agent in /etc/init.d

    ``chkconfig --list``  
    ``chkconfig --add zabbix-agent``  
    ``chkconfig zabbix-agent on``  
    ``service zabbix-agent start``

