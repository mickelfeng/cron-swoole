# cron-swoole
1.使用方法
    ```
        php Main.php {start|stop|reload} [-d]
    ```
    - start :表示启动计划任务

    - reload:表示你修改了计划任务文件，重新载入文件

    - stop  :表示停止计划任务

    - -d    :表示是否以守护进程运行

    task里面是计划任务文件，启动以后，只用把计划任务文件放入文件夹就可以了，程序会自动去发现，并启动计划任务

    task文件命名的(_ 下划线)的前部表示计划任务的启动间隔时间

    计划任务文件都是继承基类，并实现了run方法，最后返回实现类实例

    如果删掉计划任务文件，程序会自动停止该计划任务


2.说明
    #### 该程序主程序是守护程序，计划任务子程序死掉会自动重启，可以不用再守护了，但是为了避免主守护程序死掉，可以用daemon.sh这个程序去守护一下主进程
