# nfs-docker

## Create directory named **nfs** and create a docker volume with it:

```bash
mkdir nfs
docker volume create \
  --name nfs \
  --opt type=tmpfs \
  --opt device=$(pwd)/nfs \
  --opt o=bind
```

## Running it

```bash
sudo docker-compose up -d
```

## Test

#### Open bash for server

```bash
docker exec  -it server /bin/bash
```

#### Create a `test.txt` file
```bash
echo "hello" > /nfs/home/test.txt
```


#### Open bash for client

```bash
docker exec  -it client /bin/bash
```

#### Opne `test.txt` file
```bash
cat /home/test.txt
```

You should see `hello` in the terminal.

