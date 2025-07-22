Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Install the latest PowerShell for new features and improvements! https://aka.ms/PSWindows

PS C:\Users\utpla> ssh lab-user@lab-as-19145.lc.cl-labs.springpeople.com
lab-user@lab-as-19145.lc.cl-labs.springpeople.com's password:
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.8.0-1024-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Tue Jul 22 07:11:41 UTC 2025

  System load:           0.0
  Usage of /:            14.8% of 48.27GB
  Memory usage:          11%
  Swap usage:            0%
  Temperature:           -273.1 C
  Processes:             216
  Users logged in:       1
  IPv4 address for ens5: 172.31.115.193
  IPv6 address for ens5: 2406:da1b:cd6:7ed5:4ca3:f13e:c082:96b3

 * Ubuntu Pro delivers the most comprehensive open source security and
   compliance features.

   https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

261 updates can be applied immediately.
147 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Tue Jul 22 07:08:36 2025 from 49.207.200.12
lab-user@ip-172-31-115-193:~$ sudo -i
[sudo] password for lab-user:
[root@ip-172-31-115-193 ~]$ docker --version
Docker version 28.3.2, build 578ccf6
[root@ip-172-31-115-193 ~]$ docker infp
docker: unknown command: docker infp

Run 'docker --help' for more information
[root@ip-172-31-115-193 ~]$ docker info
Client: Docker Engine - Community
 Version:    28.3.2
 Context:    default
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.25.0
    Path:     /usr/libexec/docker/cli-plugins/docker-buildx
  compose: Docker Compose (Docker Inc.)
    Version:  v2.38.2
    Path:     /usr/libexec/docker/cli-plugins/docker-compose

Server:
 Containers: 1
  Running: 0
  Paused: 0
  Stopped: 1
 Images: 1
 Server Version: 28.3.2
 Storage Driver: overlay2
  Backing Filesystem: extfs
  Supports d_type: true
  Using metacopy: false
  Native Overlay Diff: true
  userxattr: false
 Logging Driver: json-file
 Cgroup Driver: systemd
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 05044ec0a9a75232cad458027ca83437aae3f4da
 runc version: v1.2.5-0-g59923ef
 init version: de40ad0
 Security Options:
  apparmor
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.8.0-1024-aws
 Operating System: Ubuntu 24.04.2 LTS
 OSType: linux
 Architecture: x86_64
 CPUs: 2
 Total Memory: 7.657GiB
 Name: ip-172-31-115-193
 ID: 57ab25c1-2823-4081-9eba-4db09017d450
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 Experimental: false
 Insecure Registries:
  ::1/128
  127.0.0.0/8
 Live Restore Enabled: false

[root@ip-172-31-115-193 ~]$ docker container run --publish 80:80 --detach nginx
d3e14c115703f7a84e684e91425c96c5084f6001d3f9a93298e854dee155aa8c
docker: Error response from daemon: failed to set up container networking: driver failed programming external connectivity on endpoint thirsty_napier (138958956b81990b6ba57021c32f00062ef747a4e92ad91bcea4e16f1769f37a): Bind for 0.0.0.0:80 failed: port is already allocated

Run 'docker run --help' for more information
[root@ip-172-31-115-193 ~]$ docker run --help
Usage:  docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

Create and run a new container from an image

Aliases:
  docker container run, docker run

Options:
      --add-host list                    Add a custom host-to-IP mapping (host:ip)
      --annotation map                   Add an annotation to the container (passed through to the OCI runtime) (default map[])
  -a, --attach list                      Attach to STDIN, STDOUT or STDERR
      --blkio-weight uint16              Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0)
      --blkio-weight-device list         Block IO weight (relative device weight) (default [])
      --cap-add list                     Add Linux capabilities
      --cap-drop list                    Drop Linux capabilities
      --cgroup-parent string             Optional parent cgroup for the container
      --cgroupns string                  Cgroup namespace to use (host|private)
                                         'host':    Run the container in the Docker host's cgroup namespace
                                         'private': Run the container in its own private cgroup namespace
                                         '':        Use the cgroup namespace as configured by the
                                                    default-cgroupns-mode option on the daemon (default)
      --cidfile string                   Write the container ID to the file
      --cpu-period int                   Limit CPU CFS (Completely Fair Scheduler) period
      --cpu-quota int                    Limit CPU CFS (Completely Fair Scheduler) quota
      --cpu-rt-period int                Limit CPU real-time period in microseconds
      --cpu-rt-runtime int               Limit CPU real-time runtime in microseconds
  -c, --cpu-shares int                   CPU shares (relative weight)
      --cpus decimal                     Number of CPUs
      --cpuset-cpus string               CPUs in which to allow execution (0-3, 0,1)
      --cpuset-mems string               MEMs in which to allow execution (0-3, 0,1)
  -d, --detach                           Run container in background and print container ID
      --detach-keys string               Override the key sequence for detaching a container
      --device list                      Add a host device to the container
      --device-cgroup-rule list          Add a rule to the cgroup allowed devices list
      --device-read-bps list             Limit read rate (bytes per second) from a device (default [])
      --device-read-iops list            Limit read rate (IO per second) from a device (default [])
      --device-write-bps list            Limit write rate (bytes per second) to a device (default [])
      --device-write-iops list           Limit write rate (IO per second) to a device (default [])
      --disable-content-trust            Skip image verification (default true)
      --dns list                         Set custom DNS servers
      --dns-option list                  Set DNS options
      --dns-search list                  Set custom DNS search domains
      --domainname string                Container NIS domain name
      --entrypoint string                Overwrite the default ENTRYPOINT of the image
  -e, --env list                         Set environment variables
      --env-file list                    Read in a file of environment variables
      --expose list                      Expose a port or a range of ports
      --gpus gpu-request                 GPU devices to add to the container ('all' to pass all GPUs)
      --group-add list                   Add additional groups to join
      --health-cmd string                Command to run to check health
      --health-interval duration         Time between running the check (ms|s|m|h) (default 0s)
      --health-retries int               Consecutive failures needed to report unhealthy
      --health-start-interval duration   Time between running the check during the start period (ms|s|m|h) (default 0s)
      --health-start-period duration     Start period for the container to initialize before starting health-retries countdown (ms|s|m|h) (default 0s)
      --health-timeout duration          Maximum time to allow one check to run (ms|s|m|h) (default 0s)
      --help                             Print usage
  -h, --hostname string                  Container host name
      --init                             Run an init inside the container that forwards signals and reaps processes
  -i, --interactive                      Keep STDIN open even if not attached
      --ip string                        IPv4 address (e.g., 172.30.100.104)
      --ip6 string                       IPv6 address (e.g., 2001:db8::33)
      --ipc string                       IPC mode to use
      --isolation string                 Container isolation technology
      --kernel-memory bytes              Kernel memory limit
  -l, --label list                       Set meta data on a container
      --label-file list                  Read in a line delimited file of labels
      --link list                        Add link to another container
      --link-local-ip list               Container IPv4/IPv6 link-local addresses
      --log-driver string                Logging driver for the container
      --log-opt list                     Log driver options
      --mac-address string               Container MAC address (e.g., 92:d0:c6:0a:29:33)
  -m, --memory bytes                     Memory limit
      --memory-reservation bytes         Memory soft limit
      --memory-swap bytes                Swap limit equal to memory plus swap: '-1' to enable unlimited swap
      --memory-swappiness int            Tune container memory swappiness (0 to 100) (default -1)
      --mount mount                      Attach a filesystem mount to the container
      --name string                      Assign a name to the container
      --network network                  Connect a container to a network
      --network-alias list               Add network-scoped alias for the container
      --no-healthcheck                   Disable any container-specified HEALTHCHECK
      --oom-kill-disable                 Disable OOM Killer
      --oom-score-adj int                Tune host's OOM preferences (-1000 to 1000)
      --pid string                       PID namespace to use
      --pids-limit int                   Tune container pids limit (set -1 for unlimited)
      --platform string                  Set platform if server is multi-platform capable
      --privileged                       Give extended privileges to this container
  -p, --publish list                     Publish a container's port(s) to the host
  -P, --publish-all                      Publish all exposed ports to random ports
      --pull string                      Pull image before running ("always", "missing", "never") (default "missing")
  -q, --quiet                            Suppress the pull output
      --read-only                        Mount the container's root filesystem as read only
      --restart string                   Restart policy to apply when a container exits (default "no")
      --rm                               Automatically remove the container and its associated anonymous volumes when it exits
      --runtime string                   Runtime to use for this container
      --security-opt list                Security Options
      --shm-size bytes                   Size of /dev/shm
      --sig-proxy                        Proxy received signals to the process (default true)
      --stop-signal string               Signal to stop the container
      --stop-timeout int                 Timeout (in seconds) to stop a container
      --storage-opt list                 Storage driver options for the container
      --sysctl map                       Sysctl options (default map[])
      --tmpfs list                       Mount a tmpfs directory
  -t, --tty                              Allocate a pseudo-TTY
      --ulimit ulimit                    Ulimit options (default [])
      --use-api-socket                   Bind mount Docker API socket and required auth
  -u, --user string                      Username or UID (format: <name|uid>[:<group|gid>])
      --userns string                    User namespace to use
      --uts string                       UTS namespace to use
  -v, --volume list                      Bind mount a volume
      --volume-driver string             Optional volume driver for the container
      --volumes-from list                Mount volumes from the specified container(s)
  -w, --workdir string                   Working directory inside the container
[root@ip-172-31-115-193 ~]$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                                 NAMES
c46c1ac6e290   nginx     "/docker-entrypoint.…"   4 minutes ago   Up 4 minutes   0.0.0.0:80->80/tcp, [::]:80->80/tcp   dreamy_raman
[root@ip-172-31-115-193 ~]$ docker container run --publish 81:80 --detach nginx
b41c42ee81705c887ec36356a1241dee3ea3470df68c69ba1d0a44f6f7105d2d
[root@ip-172-31-115-193 ~]$ docker image
Usage:  docker image COMMAND

Manage images

Commands:
  build       Build an image from a Dockerfile
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Display detailed information on one or more images
  load        Load an image from a tar archive or STDIN
  ls          List images
  prune       Remove unused images
  pull        Download an image from a registry
  push        Upload an image to a registry
  rm          Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

Run 'docker image COMMAND --help' for more information on a command.
[root@ip-172-31-115-193 ~]$ docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
nginx         latest    2cd1d97f893f   7 days ago     192MB
hello-world   latest    74cc54e27dc4   6 months ago   10.1kB
[root@ip-172-31-115-193 ~]$ docker container run --pubish 80:80 --detach nginx
unknown flag: --pubish

Usage:  docker container run [OPTIONS] IMAGE [COMMAND] [ARG...]

Run 'docker container run --help' for more information
[root@ip-172-31-115-193 ~]$ docker container run --publish 80:80 --detach nginx
ba1b0c575926fd23d148484094cf659070e10d151010975f9cc356ce2faef519
docker: Error response from daemon: failed to set up container networking: driver failed programming external connectivity on endpoint ecstatic_jepsen (335da15c12f7795e9c0476c72f53d0a6de66f1737a8e25519b3ce1a59fa10ed8): Bind for 0.0.0.0:80 failed: port is already allocated

Run 'docker run --help' for more information
[root@ip-172-31-115-193 ~]$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                 NAMES
b41c42ee8170   nginx     "/docker-entrypoint.…"   5 minutes ago    Up 5 minutes    0.0.0.0:81->80/tcp, [::]:81->80/tcp   friendly_driscoll
c46c1ac6e290   nginx     "/docker-entrypoint.…"   10 minutes ago   Up 10 minutes   0.0.0.0:80->80/tcp, [::]:80->80/tcp   dreamy_raman
[root@ip-172-31-115-193 ~]$ curl localhost
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
[root@ip-172-31-115-193 ~]$ client_loop: send disconnect: Connection reset
PS C:\Users\utpla> ssh lab-user@lab-as-19145.lc.cl-labs.springpeople.com
lab-user@lab-as-19145.lc.cl-labs.springpeople.com's password:
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.8.0-1024-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Tue Jul 22 08:46:01 UTC 2025

  System load:           0.0
  Usage of /:            15.2% of 48.27GB
  Memory usage:          12%
  Swap usage:            0%
  Temperature:           -273.1 C
  Processes:             249
  Users logged in:       1
  IPv4 address for ens5: 172.31.115.193
  IPv6 address for ens5: 2406:da1b:cd6:7ed5:4ca3:f13e:c082:96b3

 * Ubuntu Pro delivers the most comprehensive open source security and
   compliance features.

   https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

261 updates can be applied immediately.
147 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Tue Jul 22 08:36:31 2025 from 49.207.200.12
lab-user@ip-172-31-115-193:~$ sudo -i
[sudo] password for lab-user:
[root@ip-172-31-115-193 ~]$ docker run --name mongo -d mongo
Unable to find image 'mongo:latest' locally
latest: Pulling from library/mongo
32f112e3802c: Pull complete
9a9cb08d2643: Pull complete
253e6c802ed4: Pull complete
18187a229a5f: Pull complete
0933c7d186fd: Pull complete
dd7affbc51f8: Pull complete
8162d2288420: Pull complete
6c341662e12b: Pull complete
Digest: sha256:dca8d11fe4673f4409e27361e9c5717bd35103c9c15b5b50fc6b2913b2407fed
Status: Downloaded newer image for mongo:latest
docker: Error response from daemon: Conflict. The container name "/mongo" is already in use by container "ff23a06a56e6be12e1da8f45a80607052282a015cb83deb2c9ccd26862fd2473". You have to remove (or rename) that container to be able to reuse that name.

Run 'docker run --help' for more information
[root@ip-172-31-115-193 ~]$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED             STATUS             PORTS                                 NAMES
ff23a06a56e6   mongo     "docker-entrypoint.s…"   6 seconds ago       Up 4 seconds       27017/tcp                             mongo
b41c42ee8170   nginx     "/docker-entrypoint.…"   About an hour ago   Up About an hour   0.0.0.0:81->80/tcp, [::]:81->80/tcp   friendly_driscoll
c46c1ac6e290   nginx     "/docker-entrypoint.…"   2 hours ago         Up 2 hours         0.0.0.0:80->80/tcp, [::]:80->80/tcp   dreamy_raman
[root@ip-172-31-115-193 ~]$ docker top mongo
UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
lxd                 9956                9933                1                   08:46               ?                   00:00:00            mongod --bind_ip_all
[root@ip-172-31-115-193 ~]$
[root@ip-172-31-115-193 ~]$ kill -9 9956
[root@ip-172-31-115-193 ~]$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED       STATUS       PORTS                                 NAMES
b41c42ee8170   nginx     "/docker-entrypoint.…"   2 hours ago   Up 2 hours   0.0.0.0:81->80/tcp, [::]:81->80/tcp   friendly_driscoll
c46c1ac6e290   nginx     "/docker-entrypoint.…"   2 hours ago   Up 2 hours   0.0.0.0:80->80/tcp, [::]:80->80/tcp   dreamy_raman
[root@ip-172-31-115-193 ~]$ docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED             STATUS                        PORTS                                 NAMES
ff23a06a56e6   mongo         "docker-entrypoint.s…"   3 minutes ago       Exited (137) 16 seconds ago                                         mongo
ba1b0c575926   nginx         "/docker-entrypoint.…"   About an hour ago   Created                                                             ecstatic_jepsen
3e66fa38b3ff   nginx         "/docker-entrypoint.…"   About an hour ago   Created                                                             recursing_herschel
b41c42ee8170   nginx         "/docker-entrypoint.…"   2 hours ago         Up 2 hours                    0.0.0.0:81->80/tcp, [::]:81->80/tcp   friendly_driscoll
d3e14c115703   nginx         "/docker-entrypoint.…"   2 hours ago         Created                                                             thirsty_napier
c46c1ac6e290   nginx         "/docker-entrypoint.…"   2 hours ago         Up 2 hours                    0.0.0.0:80->80/tcp, [::]:80->80/tcp   dreamy_raman
cabbde5cc27a   hello-world   "/hello"                 2 hours ago         Exited (0) 2 hours ago                                              competent_pare
[root@ip-172-31-115-193 ~]$ client_loop: send disconnect: Connection reset
PS C:\Users\utpla> ssh lab-user@lab-as-19145.lc.cl-labs.springpeople.com
lab-user@lab-as-19145.lc.cl-labs.springpeople.com's password:
Welcome to Ubuntu 24.04.2 LTS (GNU/Linux 6.8.0-1024-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Tue Jul 22 09:04:18 UTC 2025

  System load:           0.0
  Usage of /:            17.4% of 48.27GB
  Memory usage:          12%
  Swap usage:            0%
  Temperature:           -273.1 C
  Processes:             262
  Users logged in:       1
  IPv4 address for ens5: 172.31.115.193
  IPv6 address for ens5: 2406:da1b:cd6:7ed5:4ca3:f13e:c082:96b3

 * Ubuntu Pro delivers the most comprehensive open source security and
   compliance features.

   https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

261 updates can be applied immediately.
147 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Tue Jul 22 08:46:11 2025 from 49.207.200.12
lab-user@ip-172-31-115-193:~$ sudo -i
[sudo] password for lab-user:
[root@ip-172-31-115-193 ~]$ docker container run -d -p 3306:3305 --name db -e MYSQL_ROOT_PASSWORD=true mysql
Unable to find image 'mysql:latest' locally
latest: Pulling from library/mysql
62efe2b176c9: Pull complete
58e04d708861: Pull complete
a0ab11061beb: Pull complete
d63fd583f69a: Pull complete
7415b6255bc3: Pull complete
82954a2a5cc3: Pull complete
fd23d224f5e0: Pull complete
ca070ddf1d20: Pull complete
c334fa4b946c: Pull complete
36af822b21e5: Pull complete
Digest: sha256:b9d8b7ec6e6aced08b1cfe50776f8e323c0a625adf4e10e69f90fc686ea10807
Status: Downloaded newer image for mysql:latest
a5314d36aa39b6e6034276e1f8e8764b6043cf6713c0c871d6cccd3efcd419ed
[root@ip-172-31-115-193 ~]$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                                              NAMES
a5314d36aa39   mysql     "docker-entrypoint.s…"   17 seconds ago   Up 13 seconds   3306/tcp, 33060/tcp, 0.0.0.0:3306->3305/tcp, [::]:3306->3305/tcp   db
b41c42ee8170   nginx     "/docker-entrypoint.…"   2 hours ago      Up 2 hours      0.0.0.0:81->80/tcp, [::]:81->80/tcp                                friendly_driscoll
c46c1ac6e290   nginx     "/docker-entrypoint.…"   2 hours ago      Up 2 hours      0.0.0.0:80->80/tcp, [::]:80->80/tcp                                dreamy_raman
[root@ip-172-31-115-193 ~]$ docker logs db
2025-07-22 09:08:48+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 9.3.0-1.el9 started.
2025-07-22 09:08:49+00:00 [Note] [Entrypoint]: Switching to dedicated user 'mysql'
2025-07-22 09:08:49+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 9.3.0-1.el9 started.
2025-07-22 09:08:49+00:00 [Note] [Entrypoint]: Initializing database files
2025-07-22T09:08:49.416638Z 0 [System] [MY-015017] [Server] MySQL Server Initialization - start.
2025-07-22T09:08:49.418237Z 0 [System] [MY-013169] [Server] /usr/sbin/mysqld (mysqld 9.3.0) initializing of server in progress as process 79
2025-07-22T09:08:49.426230Z 1 [System] [MY-013576] [InnoDB] InnoDB initialization has started.
2025-07-22T09:08:50.074268Z 1 [System] [MY-013577] [InnoDB] InnoDB initialization has ended.
2025-07-22T09:08:51.499645Z 6 [Warning] [MY-010453] [Server] root@localhost is created with an empty password ! Please consider switching off the --initialize-insecure option.
2025-07-22T09:08:54.007694Z 0 [System] [MY-015018] [Server] MySQL Server Initialization - end.
2025-07-22 09:08:54+00:00 [Note] [Entrypoint]: Database files initialized
2025-07-22 09:08:54+00:00 [Note] [Entrypoint]: Starting temporary server
2025-07-22T09:08:54.049747Z 0 [System] [MY-015015] [Server] MySQL Server - start.
2025-07-22T09:08:54.341539Z 0 [System] [MY-010116] [Server] /usr/sbin/mysqld (mysqld 9.3.0) starting as process 118
2025-07-22T09:08:54.359836Z 1 [System] [MY-013576] [InnoDB] InnoDB initialization has started.
2025-07-22T09:08:54.868678Z 1 [System] [MY-013577] [InnoDB] InnoDB initialization has ended.
2025-07-22T09:08:55.294209Z 0 [Warning] [MY-010068] [Server] CA certificate ca.pem is self signed.
2025-07-22T09:08:55.294246Z 0 [System] [MY-013602] [Server] Channel mysql_main configured to support TLS. Encrypted connections are now supported for this channel.
2025-07-22T09:08:55.298684Z 0 [Warning] [MY-011810] [Server] Insecure configuration for --pid-file: Location '/var/run/mysqld' in the path is accessible to all OS users. Consider choosing a different directory.
2025-07-22T09:08:55.337117Z 0 [System] [MY-011323] [Server] X Plugin ready for connections. Socket: /var/run/mysqld/mysqlx.sock
2025-07-22T09:08:55.337180Z 0 [System] [MY-010931] [Server] /usr/sbin/mysqld: ready for connections. Version: '9.3.0'  socket: '/var/run/mysqld/mysqld.sock'  port: 0  MySQL Community Server - GPL.
2025-07-22 09:08:55+00:00 [Note] [Entrypoint]: Temporary server started.
'/var/lib/mysql/mysql.sock' -> '/var/run/mysqld/mysqld.sock'
Warning: Unable to load '/usr/share/zoneinfo/iso3166.tab' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/leap-seconds.list' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/leapseconds' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/tzdata.zi' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/zone.tab' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/zone1970.tab' as time zone. Skipping it.

2025-07-22 09:08:57+00:00 [Note] [Entrypoint]: Stopping temporary server
2025-07-22T09:08:57.021896Z 11 [System] [MY-013172] [Server] Received SHUTDOWN from user root. Shutting down mysqld (Version: 9.3.0).
2025-07-22T09:08:57.686280Z 0 [System] [MY-010910] [Server] /usr/sbin/mysqld: Shutdown complete (mysqld 9.3.0)  MySQL Community Server - GPL.
2025-07-22T09:08:57.686299Z 0 [System] [MY-015016] [Server] MySQL Server - end.
2025-07-22 09:08:58+00:00 [Note] [Entrypoint]: Temporary server stopped

2025-07-22 09:08:58+00:00 [Note] [Entrypoint]: MySQL init process done. Ready for start up.

2025-07-22T09:08:58.044366Z 0 [System] [MY-015015] [Server] MySQL Server - start.
2025-07-22T09:08:58.340407Z 0 [System] [MY-010116] [Server] /usr/sbin/mysqld (mysqld 9.3.0) starting as process 1
2025-07-22T09:08:58.347037Z 1 [System] [MY-013576] [InnoDB] InnoDB initialization has started.
2025-07-22T09:08:58.860367Z 1 [System] [MY-013577] [InnoDB] InnoDB initialization has ended.
2025-07-22T09:08:59.201831Z 0 [Warning] [MY-010068] [Server] CA certificate ca.pem is self signed.
2025-07-22T09:08:59.201867Z 0 [System] [MY-013602] [Server] Channel mysql_main configured to support TLS. Encrypted connections are now supported for this channel.
2025-07-22T09:08:59.206030Z 0 [Warning] [MY-011810] [Server] Insecure configuration for --pid-file: Location '/var/run/mysqld' in the path is accessible to all OS users. Consider choosing a different directory.
2025-07-22T09:08:59.246384Z 0 [System] [MY-011323] [Server] X Plugin ready for connections. Bind-address: '::' port: 33060, socket: /var/run/mysqld/mysqlx.sock
2025-07-22T09:08:59.246474Z 0 [System] [MY-010931] [Server] /usr/sbin/mysqld: ready for connections. Version: '9.3.0'  socket: '/var/run/mysqld/mysqld.sock'  port: 3306  MySQL Community Server - GPL.
[root@ip-172-31-115-193 ~]$ docker exec -it db bash
bash-5.1# mysql
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: NO)
bash-5.1# Welcome@123
bash: Welcome@123: command not found
bash-5.1# create database employee
bash: create: command not found
bash-5.1# exit
exit
[root@ip-172-31-115-193 ~]$ docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=true mysq
Unable to find image 'mysq:latest' locally
docker: Error response from daemon: pull access denied for mysq, repository does not exist or may require 'docker login': denied: requested access to the resource is denied

Run 'docker run --help' for more information
[root@ip-172-31-115-193 ~]$ docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=true mysql
docker: Error response from daemon: Conflict. The container name "/db" is already in use by container "a5314d36aa39b6e6034276e1f8e8764b6043cf6713c0c871d6cccd3efcd419ed". You have to remove (or rename) that container to be able to reuse that name.

Run 'docker run --help' for more information
[root@ip-172-31-115-193 ~]$ docker exec -it db bash
bash-5.1# mysql -u root -p
Enter password:
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: NO)
bash-5.1# NO
bash: NO: command not found
bash-5.1# exit
exit
[root@ip-172-31-115-193 ~]$ docker rm db --force
db
[root@ip-172-31-115-193 ~]$ docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=true mysql
docker: Error response from daemon: Conflict. The container name "/db" is already in use by container "3cb6c0080571c21abf5e620569ef8d41808ddca184821ae0f02a98dba30f4bc3". You have to remove (or rename) that container to be able to reuse that name.

Run 'docker run --help' for more information
[root@ip-172-31-115-193 ~]$ docker rm -f db
db
[root@ip-172-31-115-193 ~]$ docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=true mysql
4955cbe84860f256a0bedae0903ed090d1d7be53566d438c3cb70f0e26d6d216
[root@ip-172-31-115-193 ~]$ docker exec -it db bash
bash-5.1# mysql -u root -p
Enter password:
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
bash-5.1# mysql -u root -p
Enter password:
ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES)
bash-5.1# exit
exit
[root@ip-172-31-115-193 ~]$ docker rm -f db
db
[root@ip-172-31-115-193 ~]$ docker ls
docker: unknown command: docker ls

Run 'docker --help' for more information
[root@ip-172-31-115-193 ~]$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED       STATUS       PORTS                                 NAMES
b41c42ee8170   nginx     "/docker-entrypoint.…"   2 hours ago   Up 2 hours   0.0.0.0:81->80/tcp, [::]:81->80/tcp   friendly_driscoll
c46c1ac6e290   nginx     "/docker-entrypoint.…"   2 hours ago   Up 2 hours   0.0.0.0:80->80/tcp, [::]:80->80/tcp   dreamy_raman
[root@ip-172-31-115-193 ~]$ docker container run -d -p 3306:3306 --name db -e MYSQL_RANDOM_ROOT_PASSWORD=true mysql
d84c82115d16653e71b412d66eb16c17cf135f776d722bdaf33f53cd3e957a5b
[root@ip-172-31-115-193 ~]$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                                    NAMES
d84c82115d16   mysql     "docker-entrypoint.s…"   14 seconds ago   Up 13 seconds   0.0.0.0:3306->3306/tcp, [::]:3306->3306/tcp, 33060/tcp   db
b41c42ee8170   nginx     "/docker-entrypoint.…"   2 hours ago      Up 2 hours      0.0.0.0:81->80/tcp, [::]:81->80/tcp                      friendly_driscoll
c46c1ac6e290   nginx     "/docker-entrypoint.…"   2 hours ago      Up 2 hours      0.0.0.0:80->80/tcp, [::]:80->80/tcp                      dreamy_raman
[root@ip-172-31-115-193 ~]$ docker logs db
2025-07-22 09:22:27+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 9.3.0-1.el9 started.
2025-07-22 09:22:27+00:00 [Note] [Entrypoint]: Switching to dedicated user 'mysql'
2025-07-22 09:22:27+00:00 [Note] [Entrypoint]: Entrypoint script for MySQL Server 9.3.0-1.el9 started.
2025-07-22 09:22:27+00:00 [Note] [Entrypoint]: Initializing database files
2025-07-22T09:22:27.874487Z 0 [System] [MY-015017] [Server] MySQL Server Initialization - start.
2025-07-22T09:22:27.876019Z 0 [System] [MY-013169] [Server] /usr/sbin/mysqld (mysqld 9.3.0) initializing of server in progress as process 79
2025-07-22T09:22:27.884285Z 1 [System] [MY-013576] [InnoDB] InnoDB initialization has started.
2025-07-22T09:22:28.523033Z 1 [System] [MY-013577] [InnoDB] InnoDB initialization has ended.
2025-07-22T09:22:29.855441Z 6 [Warning] [MY-010453] [Server] root@localhost is created with an empty password ! Please consider switching off the --initialize-insecure option.
2025-07-22T09:22:32.465287Z 0 [System] [MY-015018] [Server] MySQL Server Initialization - end.
2025-07-22 09:22:32+00:00 [Note] [Entrypoint]: Database files initialized
2025-07-22 09:22:32+00:00 [Note] [Entrypoint]: Starting temporary server
2025-07-22T09:22:32.506046Z 0 [System] [MY-015015] [Server] MySQL Server - start.
2025-07-22T09:22:32.802960Z 0 [System] [MY-010116] [Server] /usr/sbin/mysqld (mysqld 9.3.0) starting as process 118
2025-07-22T09:22:32.822547Z 1 [System] [MY-013576] [InnoDB] InnoDB initialization has started.
2025-07-22T09:22:33.343049Z 1 [System] [MY-013577] [InnoDB] InnoDB initialization has ended.
2025-07-22T09:22:33.771122Z 0 [Warning] [MY-010068] [Server] CA certificate ca.pem is self signed.
2025-07-22T09:22:33.771158Z 0 [System] [MY-013602] [Server] Channel mysql_main configured to support TLS. Encrypted connections are now supported for this channel.
2025-07-22T09:22:33.775465Z 0 [Warning] [MY-011810] [Server] Insecure configuration for --pid-file: Location '/var/run/mysqld' in the path is accessible to all OS users. Consider choosing a different directory.
2025-07-22T09:22:33.812394Z 0 [System] [MY-011323] [Server] X Plugin ready for connections. Socket: /var/run/mysqld/mysqlx.sock
2025-07-22T09:22:33.812457Z 0 [System] [MY-010931] [Server] /usr/sbin/mysqld: ready for connections. Version: '9.3.0'  socket: '/var/run/mysqld/mysqld.sock'  port: 0  MySQL Community Server - GPL.
2025-07-22 09:22:33+00:00 [Note] [Entrypoint]: Temporary server started.
'/var/lib/mysql/mysql.sock' -> '/var/run/mysqld/mysqld.sock'
Warning: Unable to load '/usr/share/zoneinfo/iso3166.tab' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/leap-seconds.list' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/leapseconds' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/tzdata.zi' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/zone.tab' as time zone. Skipping it.
Warning: Unable to load '/usr/share/zoneinfo/zone1970.tab' as time zone. Skipping it.
2025-07-22 09:22:35+00:00 [Note] [Entrypoint]: GENERATED ROOT PASSWORD: xrdM87uWdgpD3q4m/bX9eW8yVGzbUkL5

2025-07-22 09:22:35+00:00 [Note] [Entrypoint]: Stopping temporary server
2025-07-22T09:22:35.504929Z 11 [System] [MY-013172] [Server] Received SHUTDOWN from user root. Shutting down mysqld (Version: 9.3.0).
2025-07-22T09:22:36.155507Z 0 [System] [MY-010910] [Server] /usr/sbin/mysqld: Shutdown complete (mysqld 9.3.0)  MySQL Community Server - GPL.
2025-07-22T09:22:36.155527Z 0 [System] [MY-015016] [Server] MySQL Server - end.
2025-07-22 09:22:36+00:00 [Note] [Entrypoint]: Temporary server stopped

2025-07-22 09:22:36+00:00 [Note] [Entrypoint]: MySQL init process done. Ready for start up.

2025-07-22T09:22:36.527183Z 0 [System] [MY-015015] [Server] MySQL Server - start.
2025-07-22T09:22:36.815441Z 0 [System] [MY-010116] [Server] /usr/sbin/mysqld (mysqld 9.3.0) starting as process 1
2025-07-22T09:22:36.821968Z 1 [System] [MY-013576] [InnoDB] InnoDB initialization has started.
2025-07-22T09:22:37.344735Z 1 [System] [MY-013577] [InnoDB] InnoDB initialization has ended.
2025-07-22T09:22:37.707649Z 0 [Warning] [MY-010068] [Server] CA certificate ca.pem is self signed.
2025-07-22T09:22:37.707688Z 0 [System] [MY-013602] [Server] Channel mysql_main configured to support TLS. Encrypted connections are now supported for this channel.
2025-07-22T09:22:37.711882Z 0 [Warning] [MY-011810] [Server] Insecure configuration for --pid-file: Location '/var/run/mysqld' in the path is accessible to all OS users. Consider choosing a different directory.
2025-07-22T09:22:37.754346Z 0 [System] [MY-011323] [Server] X Plugin ready for connections. Bind-address: '::' port: 33060, socket: /var/run/mysqld/mysqlx.sock
2025-07-22T09:22:37.754428Z 0 [System] [MY-010931] [Server] /usr/sbin/mysqld: ready for connections. Version: '9.3.0'  socket: '/var/run/mysqld/mysqld.sock'  port: 3306  MySQL Community Server - GPL.
[root@ip-172-31-115-193 ~]$ docker exec -it db bash
bash-5.1# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 9.3.0 MySQL Community Server - GPL

Copyright (c) 2000, 2025, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databased
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'databased' at line 1
mysql> show databases
    ->
    ->
    -> ;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.004 sec)

mysql> create database employee;
Query OK, 1 row affected (0.007 sec)

mysql> show database;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'database' at line 1
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| employee           |
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.001 sec)

mysql> exit
Bye
bash-5.1# exit
exit
[root@ip-172-31-115-193 ~]$
