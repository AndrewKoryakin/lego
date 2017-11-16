# kube-lego
Скрипт для установки kube-lego

1. Установка
```
curl -s https://raw.githubusercontent.com/flant/kube-lego/master/ctl.sh |bash -s - -i
```
2. Настроить ежедневное автообновление:
```
cat > /etc/cron.d/kubernetes-dashboard-updater <<END
42 3 * * * root curl -s https://raw.githubusercontent.com/flant/kube-lego/master/ctl.sh |bash -s - -u 
END
```

*Ручное обновление*
```
curl -s https://raw.githubusercontent.com/flant/kube-lego/master/ctl.sh |bash -s - -u
```

*Удаление*
```
curl -s https://raw.githubusercontent.com/flant/kube-lego/master/ctl.sh |bash -s - -d
```


Help
```
Usage: ctl.sh [OPTION]... --email GITLAB_URL 
Install kube-lego to Kubernetes cluster.
Mandatory arguments:
  -i, --install                install in kube-lego namespace 
  -u, --upgrade                upgrade existing installation
  -d, --delete                 remove everything, including the namespace
Optional arguments:
      --email                  set email default 256@flant.ru
  -h, --help                   output this message

```



