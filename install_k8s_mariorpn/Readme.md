Cluster k8s com apenas 1 controlplane e 2 workers para estudo baseado em Ubuntu.

Para usá-lo:

1 - Crie 3 VMs com ubuntu 20.04 LTS com 2 CPUs e 2GB de RAM cada.
2 - Importe a chave publica do user ROOT das VMs que criou anteriormente para o servidor ansible onde vai rodar o playbook
	# ssh-keygen -t rsa 2048
	# ssh-copy-id id_rsa.pub user@ansible-srv
3 - Cadastre os IPs das VMs no arquivo install_k8s_mariorpn/hosts
4 - Execute o playbook. Lembre-se que deve ser executado na raiz de onde está o 
	# ansible-playbook -i hosts ansible/install_k8s_mariorpn/main.yml -v
