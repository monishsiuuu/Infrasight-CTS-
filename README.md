# Infrasight-Spring-Boot
This is an Spring Boot microservice application that has provisions to connect through SSh and Grab server stats.

## Useful Commands

- Command to start a local Ubuntu server in docker
```bash
docker run -it -p 23000:3000 -p 28080:8080 -p 28000:8000 -p 24200:4200 -p 2022:22
--name ubuntu-server-2 navin3d/ubuntu-server
```

## Password approach.
- You need to change PasswordAuthentication yes change in file /etc/ssh/sshd_config to use password auth instead of private_key.

## Public key approach.
- If you are using private key auth generate a private key using this command.
```bash
ssh-keygen -t ecdsa -b 521 -C "********@gmail.com" -m pem
```
- And add this private key to the authorized_keys list in remote server using this command.
```bash
echo <YOUR-PUBLIC-KEY> >> ~/.ssh/authorized_keys
```
