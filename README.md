# graphite + grafana

```sh
install_graphite(){

	basedir=/Users/tony/Library/Docker/Volumes/graphite

	docker run -d --name graphite --restart=always       \
		-p 3080:80    --expose 80                        \
		-p 2003:2003  --expose 2003                      \
		--network graphite                               \
		-v "$basedir/conf:/opt/graphite/conf"            \
		-v "$basedir/storage:/opt/graphite/storage"      \
		graphiteapp/graphite-statsd

}

install_grafana(){

	basedir=/Users/tony/Library/Docker/Volumes/grafana

	docker run -d --name grafana --restart=always     \
		-p 3081:3000                                  \
		--network graphite                            \
		-v "$basedir/lib:/var/lib/grafana"            \
		grafana/grafana

}

install_graphite && install_grafana
```

# TODO

Use docker-compose like a sane person

