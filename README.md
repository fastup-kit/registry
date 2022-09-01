# Local registry

## install & run

```sh
git clone https://github.com/fastup-kit/registry
cd registry
./generate.pass.sh user password
docker compose up -d
```

## local configuration

```sh
docker login example.org:5000
```

if you will login in registry via ip address, like this:

```sh
docker login 192.168.1.1:5000
```

you need add this ip to "insecure-registries", in docker configuration

-   Linux: /etc/docker/daemon.json
-   Windows: ~/.docker/daemon.json

```json
{
    "insecure-registries": ["192.168.1.1:5000"]
}
```

## usage

```sh
docker tag alpine example.org:5000/alpine
docker push example.org:5000/alpine
docker pull example.org:5000/alpine
```
