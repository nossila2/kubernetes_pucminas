# Aplicação APPGues

A partir do namespace: appgues a aplicação foi segmentada em 3 elementos:

- Banco de dados (Postgres)
- Backend
- Frontend


Inicialmente deve ser criado o namespace a partir do comando:

kubectl apply -f namespace.yaml

Logo após, são excecutados os manifestos do banco de dados (Postgres) a partir do comando:

kubectl apply -f postgres*.yaml

Tão logo finalizada a execução dos manifestos do banco de dados (Postgres), dever ser executados os manifestos do backend. Para isso, deve ser excecutados os manifestos a partir do comando:

kubectl apply -f backend*.yaml

Por fim, deve ser excecutados os manifestos do frontend a partir do comando:

kubectl apply -f frontend*.yaml

Para acessar a aplicação devemos descobrir em qual node o pod do frontend está sendo executado, visto que o serviço do frontend está configurado com o tipo: NodePort. Para isso, deve ser executado o seguinte comando:

**kubectl get pods -o wide -n appgues**

No exemplo abaixo, podemos verificar que o pod do frontend está sendo executado no node srv-hml-k8nod02.


NAME                                   READY   STATUS    RESTARTS   AGE     IP           NODE              NOMINATED NODE   READINESS GATES

backend-deployment-6bb75666ff-j9pfq    1/1     Running   0          42m     10.0.1.66    srv-hml-k8nod02   <none>           <none>

backend-deployment-6bb75666ff-qpmzl    1/1     Running   0          2d5h    10.0.0.47    srv-hml-k8nod01   <none>           <none>

**frontend-deployment-8464dcbb69-sjrbk**   1/1     Running   0          2d4h    10.0.1.105   **srv-hml-k8nod02**   <none>           <none>

postgres-statefulset-0                 1/1     Running   0          2d10h   10.0.0.213   srv-hml-k8nod01   <none>           <none>


Com isso devemos acessar a aplicação através da URL: **http://srv-hml-k8nod02:30001**
