# Eduhub-kube-config

- This repository houses the kubernetes manifest files which are used by the Eduhub system.

- The manifest `secrets.yml` is used to house sensitive information for a service and is not committed to source control. It's content is encrypted through the use of [Bitnami Sealed Secrets](https://github.com/bitnami-labs/sealed-secrets) which is what is seen in the `sealed-secrets.yml` files

- Run the following command to seal a `secrets.yml` file
    ```bash  
    cat secrets.yml | kubeseal --format yaml --controller-namespace kube-system --controller-name sealed-secrets > sealed-secrets.yml
    ```