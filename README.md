## Описание

Установка сервера dnsmasq в роли DNS и конфигурация записей

## Требования

Операционная система Debian или Ubuntu

## Переменные которые можно менять

```yaml
dnsmasq_addresses: "0.0.0.0"
dnsmasq_port: "53"
dnsmasq_domain: "may.local"
dnsmasq_cache: "4096"

dnsmasq_nameserver:
  - "77.88.8.1"
  - "8.8.4.4"
  - "1.1.1.1"
```

### Описание хостов

```yaml
dnsmasq_hosts:
  - hostname: test_1
    ip: "1.2.3.4"
  - hostname: test_2
    ip: "10.20.30.40"
  - hostname: test_3
    ip: "192.168.1.2"
```

## Пример Playbook

```yaml
- hosts:
    - all
  roles:
    - { role: imbicile.dnsmasq, become: true }
```

## Если вносятся изменения в файл `/etc/hosts` то необходимо перезапускать dnsmasq

```bash
systemctl reload dnsmasq.service
```
