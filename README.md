# cicd

<p align="center">
  <a href="https://github.com/Muhammadislom">
    <img src="https://skillicons.dev/icons?i=docker,nginx,laravel,mysql,postgresql,jenkins,gitlab" />
  </a>
</p>

## Нужно создать папки для value
```
 mkdir -p /data/docker/gitlab/var/opt/gitlab
```
```
 mkdir -p /data/docker/gitlab/var/log/gitlab
```
```
 mkdir -p /data/docker/gitlab/etc/gitlab-runner
```
```
 mkdir -p /data/docker/gitlab/var/run/docker.sock
```
```
 docker-compose up -d --force-recreate && docker-compose ps
```

## Узнать пароль для учетки root из web-панели GitLab:

```
 docker exec -it cicd_gitlab_1 grep 'Password:' /etc/gitlab/initial_root_password
```

## Установить свой пороль для root. Команда из контейнера
```
 sudo gitlab-rake "gitlab:password:reset[root]"
```
## SSH

#### user
```
sshuser
```
#### password
```
docker
```

### Install GitLab Runner
Run commands in php-fprm container
```
curl -L "https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh" | bash
apt-get install gitlab-runner
apt-cache madison gitlab-runner
apt-get install gitlab-runner=15.11.0
```