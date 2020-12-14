# DigitalOcean Bastion Terraform module

Terraform module to create bastion servers on DigitalOcean.

## Requirements

| Name         | Version   |
| ------------ | --------- |
| terraform    | >= 0.12.0 |
| digitalocean | >= 2.3.0  |

## Providers

| Name         | Version  |
| ------------ | -------- |
| digitalocean | >= 2.3.0 |

## Inputs

| Name    | Description                                                    | Type   | Default            | Required |
| ------- | -------------------------------------------------------------- | ------ | ------------------ | :------: |
| region  | the region of the droplet - `doctl compute region list`        | string | ""                 |   yes    |
| image   | the image of the droplet - `doctl compute image list --public` | string | `ubuntu-20-04-x64` |    no    |
| size    | the size of the droplet - `doctl compute size list`            | string | `s-1vcpu-1gb`      |    no    |
| name    | the name of the droplet                                        | string | `bastion`          |    no    |
| vpc_id  | the ID of the VPC where the droplet will be located            | string | ""                 |   yes    |
| ssh_key |                                                                | number | null               |   yes    |
| domain  | The domain name to add the droplet (A record) to               | string | ""                 |   yes    |

## Outputs

| Name       | Description                         |
| ---------- | ----------------------------------- |
| droplet_id | the ID of the droplet               |
| private_ip | the private IP of the droplet       |
| public_ip  | the public IP of the droplet (IPv4) |

## License

MIT Licensed. See [LICENSE](LICENSE) for full details
