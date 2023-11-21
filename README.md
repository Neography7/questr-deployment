# QUESTR - Anonymous Q&A Application

<p align="center">
  <img src="https://i.imgur.com/KAhUMk0.png" alt="Logo" width="500" />
</p>

This repository contains the docker & kubernetes deployment portion of the Questr Q&A application.

## QUESTR - All Repositories

- [Frontend](https://github.com/Neography7/questr-front)
- [API Gateway](https://github.com/Neography7/questr-gateway)
- [User Microservice](https://github.com/Neography7/questr-user-srvc)
- [Auth Microservice](https://github.com/Neography7/questr-auth-srvc)
- [Question Microservice](https://github.com/Neography7/questr-question-srvc)
- [GRPC Protos](https://github.com/Neography7/questr-proto)
- [Deployment](https://github.com/Neography7/questr-deployment)

## Description

This package encapsulates Questr's Docker & Kubernetes deployment setup. Deployment is orchestrated within Kubernetes, utilizing Nginx Ingress for routing. SSL encryption is implemented using Let's Encrypt through Cert-Manager.

This configuration will be realized utilizing the repositories mentioned above. You can explore these repositories to view the codebase and configurations used in this setup.

## Installing

Firstly, create docker images.

```bash
$ docker build -t questr-frontend frontend/
$ docker build -t questr-api-gateway api-gateway/
$ docker build -t questr-auth-microservice auth-service/
$ docker build -t questr-question-microservice question-service/
$ docker build -t questr-user-microservice user-service/
```

Create namespace.

```bash
$ kubectl create namespace questr
```

Then apply kubernetes files. 

```bash
# config
$ kubectl apply -f .\config.yaml

# ssl certificate
$ kubectl apply -f .\certificate.yaml

# deployment - ingress
$ kubectl apply -f .\questr.yaml

# ..or if you want use local environment
# you can skip certificate and questr yaml
# apply this for load balancer
$ kubectl apply -f .\config.yaml
```

## License

This project is licensed under the [Beerware License](LICENSE).

If you find this project useful and we ever meet, you might consider buying me a beer in return.

## Contact

If you have any questions or feedback regarding the project, feel free to get in touch:

- Email: ilkerakyel97@gmail.com
- LinkedIn: [İlker Akyel](https://www.linkedin.com/in/ilker-akyel/)
- Website: [ilkerakyel.com](https://www.ilkerakyel.com)