# Install k3s

IS required a Database on a external server in order to get an HA solution.

In this poc we have 2 master and 2 workers and a database server with a Mariadb Database configured to accept traffic from any host.

References:

"https://rancher.com/docs/k3s/latest/en/installation/ha/"

Instalar k3s

curl -sfL "https://get.k3s.io" | sh -s - server --node-taint CriticalAddonsOnly=true:NoExecute --tls-san 192.168.50.12

export K3S_DATASTORE_ENDPOINT='mysql://username:password@tcp(192.168.50.10:3306)/Solutions'

Crear bbdd
CREATE DATABASE Solutions COLLATE latin1_swedish_ci;

Debbug
journalctl -u k3s.service

Obtener Token àra agregar workers:
sudo cat /var/lib/rancher/k3s/server/node-token

TOKEN:

Obtener kubeconfig
sudo cat /etc/rancher/k3s/k3s.yaml
