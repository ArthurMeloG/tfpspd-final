# Trabalho final de PSPD

<p align=justify>
&emsp; O presente projeto tem como objetivo desenvolver uma aplicação baseada no conceito do Jogo da Vida, integrando tecnologias que otimizem tanto sua performance quanto sua escalabilidade. Para alcançar esse objetivo, utilizamos o Hadoop e o Spark com foco na otimização do desempenho computacional, explorando técnicas de processamento distribuído. Além disso, empregamos o Kubernetes para gerenciar a elasticidade da aplicação, permitindo que ela se adapte dinamicamente às variações de carga conforme a quantidade de usuários. Dessa forma, buscamos criar um software escalável e robusto, capaz de ajustar seus recursos de maneira eficiente frente a diferentes níveis de demanda.
</p>

## Alunos

|Matrícula | Aluno |
| -- | -- |
| 19/0024950  | Arthur de Melo Garcia |
| 19/0024950 |  Eliás Yousef Santana Ali |
| 19/0027355 |  Erick Melo Vidal de Oliveira |
| 19/0047968 |  Paulo Vítor Silva Abi Acl |

## Rodar Localmente

### Código padrão
```
cd engine
gcc jogoVida.c -o jogoVida
./jogoVida
```

### Código com OMP/MPI
```
cd engine
mpicc jogoVidaOMPMPI.c -fopenmp
./a.out -lmpi -4 -fopenmo -4
```

## Iniciar cluster

```
minikube start
```

## Expor as portas

```
kubectl expose deployment elasticsearch --type=LoadBalancer --name elasticsearch --port=9200

kubectl expose deployment kibana --type=LoadBalancer --name kibana --port=5601
```

## Executar os pods

```
kubectl apply -f k8s/app.yaml
```

## Apagar os deployments e services

```
kubectl delete deployments --all
kubectl delete services --all
```

## Ver os pods

```
kubectl get pods
```

## Acessar os logs

```
kubectl logs -f nome_do_pod
```

## Executar os serviços

```
minikube service <nome-do-servico>
```
```
minikube service --all
```

## Buildar imagem docker e subir no Docker Hub

```
docker build -t <username-docker>/<nome-da-imagem>:<versao> .
docker run -p <porta-local>:<porta-do-container> <nome-da-imagem>::<versao>
docker push <username-docker>/<nome-da-imagem>:<versao>
```

## Usar imagem do Docker Hub no k8s

```
docker.io/<username-docker>/<nome-da-imagem>:<versao>
```

## Resultados

<p align=justify>
&emsp; Os resultados deste projeto podem ser encontrados neste <a href="PSPD_TF.pdf">documento</a>.
</p>
