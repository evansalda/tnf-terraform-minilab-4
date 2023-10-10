# Exercice 2

- Déclarez dans votre fichier main.tf une variable nommée environnement.

- A l'aide du Meta-Argument **count** et de conditions, crééez plusieurs instances EC2 avec les caractéristiques suivantes :
    - Nombre d'instances :
        - 4 si la valeur de la variable **environnement** est **prd**
        - 2 sinon
    - AMI : ami-0f82b13d37cd1e8cc
    - Type d'instance : 
        - t2.small si la valeur de la variable **environnement** est **prd**
        - t2.micro sinon
    - sous-réseau : nuumfactory-public-subnet-1
    - Valeur du tag "Name" : nuumfactory-ec2-conditions-XX

- Exécutez la commande **terraform plan -var="environnement=dev"** et observez le plan d’exécution généré.

- Si ce plan vous convient, exécutez la commande **terraform apply -var="environnement=dev"**.

- Vérifiez sur la [console AWS](https://689995499512.signin.aws.amazon.com/console) que 2 instances EC2 de type t2.micro ont été créées.

- Exécutez la commande terraform plan **-var="environnement=prd"** et observez le plan d'exécution.

- Si ce plan vous convient, exécutez la commande **terraform apply -var="environnement=prd"**.

- Vérifiez sur la [console AWS](https://689995499512.signin.aws.amazon.com/console) que 4 instances EC2 de type t2.small ont été créées.

Supprimez les instances EC2 via la commande **terraform destroy -auto-approve**.