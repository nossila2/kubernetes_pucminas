# Aplicação APPGues

A partir do namespace: appgues a aplicação foi segmentada em 3 elementos:

- Banco de dados (Postgres)
- Backend
- Frontend

Inicialmente deve ser criado o namespace a partir do comando:

kubectl apply -f namespace.yaml

Logo após, são excecutados os manifestos do banco de dados (Postgres) a partir do comando:

kubectl apply -f postgres*.yaml

Tão logo finalizada a execução dos manifestos do banco de dados (Postgres), dever ser executados os manifestos do backend. Para isso deve ser excecutados os manifestos a partir do comando:

kubectl apply -f backend*.yaml

Por fim deve ser excecutados os manifestos do frontend a partir do comando:

kubectl apply -f frontend*.yaml



