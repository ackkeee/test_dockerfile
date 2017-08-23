# test_dockerfile

### Execution procedure

1. docker-compose build
2. docker-compose up -d
3. docker exec -it docker_jenkins_1 cat /var/lib/jenkins/secrets/initialAdminPassword
