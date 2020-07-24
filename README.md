# Docker environments for using rails template

## Run
```bash
# start docker service
sudo docker-compose run --service-ports backend
# create app using template
rails new blog -T\
  -d postgresql \
  -m /rails-template/template.rb 
```

## Other commands
```bash
# get dev container id, its container name is just list xxx_dev_run_xxx
sudo docker-compose container ps
# attach to dev container
sudo docker exec -it dev-container-id /bin/bash
# Run command in running service with not root user 
sudo docker-compose exec --user $(id -u):$(id -g) service-name /bin/bash
```

## TIPS
1. Once something in Dockerfile change, such as Gemfile, you need to rebuild the container.

```bash
sudo docker-compose down
sudo docker-compose up --build #rebuild
```

