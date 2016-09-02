Logging in your existing Docker containers with rsyslog

This project includes the following components:
- rsyslog server (log collector)
- rsyslog agent (docker container that forwards your logs to log collector)
- nginx (docker container with nginx that forwards nginx logs to log collector)

To use the docker-compose.yml file, you will need to have done the following:

1 Download and Install docker. Download and Install docker.
 - linux https://docs.docker.com/engine/installation/linux/ubuntulinux/
 - Mac https://download.docker.com/mac/beta/Docker.dmg
 - Windows 7 not supported!!!
 - Windows 10 https://download.docker.com/win/beta/InstallDocker.msi
 - Download and Install docker-compose v =>1.7.1

2 Open a shell prompt and cd into the folder containing the docker-compose.yml.

3 Pull docker images 'docker-compose pull'.

4 Start project 'docker-compose up app'.

Additional For access to logfiles you must got to directory "./log/" .  using the folowing command:
tail -f *.log

For access to rsyslog server container console you must enter following command:
  docker-compose exec rsyslog_server bash
For access to rsyslog agent container console you must enter following command:
  docker-compose exec rsyslog_agent bash
For access to rsyslog agent container console you must enter following command:
  docker-compose exec nginx sh
