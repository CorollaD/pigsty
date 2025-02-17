# PostgREST

This is an example of creating pigsty cmdb API with PostgREST

```bash
cd ~/pigsty/app/postgrest ; docker-compose up -d
```

http://10.10.10.10:8884 is the default endpoint for PostgREST

http://10.10.10.10:8883 is the default api docs for PostgREST


```bash
make up         # pull up postgrest with docker-compose
make run        # launch postgrest with docker
make ui         # run swagger ui container
make view       # print postgrest access point
make log        # tail -f postgrest logs
make info       # introspect postgrest with jq
make stop       # stop postgrest container
make clean      # remove postgrest container
make rmui       # remove swagger ui container
make pull       # pull latest postgrest image
make rmi        # remove postgrest image
make save       # save postgrest image to /tmp/postgrest.tgz
make load       # load postgrest image from /tmp
```


## Swagger UI

Launch a swagger OpenAPI UI and visualize PostgREST API on 8883 with: 

```bash
docker run --init --name postgrest --name swagger -p 8883:8080 -e API_URL=http://10.10.10.10:8884 swaggerapi/swagger-ui
# docker run -d -e API_URL=http://10.10.10.10:8884 -p 8883:8080 swaggerapi/swagger-editor # swagger editor
```

Check [http://10.10.10.10:8883/](http://10.10.10.10:8883/)
