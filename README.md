## 

Based on [this git repo](https://github.com/nicolargo/docker-influxdb-grafana.git)

Get the stack (only once):

```
git clone https://github.com/nicolargo/docker-influxdb-grafana.git
cd docker-influxdb-grafana
docker pull grafana/grafana
docker pull influxdb
docker pull telegraf
```

Run your stack:

```
sudo mkdir -p /srv/docker/grafana/data
docker-compose up -d
sudo chown -R 472:472 /srv/docker/grafana/data

```

Show me the logs:

```
docker-compose logs
```

Stop it:

```
docker-compose stop
docker-compose rm
```

Update it:

```
git pull
docker pull grafana/grafana
docker pull influxdb
docker pull telegraf
```

If you want to run Telegraf, edit the telegraf.conf to yours needs and:

```
docker exec telegraf telegraf
```

#Open your browser to http://localhost:3000
#default login is admin:admin

## Configuration
### Grafana
Edit the file ./etc/grafana.ini

Set [server] root_url = http://#.#.#.#:3000

To use grafana alerting:
configure [smtp]
enabled = true
host = #.#.#.#:25

