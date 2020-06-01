create vpc

```
ansible-playbook -i inventories/dev main.yml --connection=local --extra-vars "srv_group=localhost" --vault-password-file ~/.ansible/vaultfile --tags "create_vpc"
```

delete vpc

uncomment vars_prompt in main.yml

run deleting
```
ansible-playbook -i inventories/dev main.yml --connection=local --extra-vars "srv_group=localhost" --vault-password-file ~/.ansible/vaultfile --tags "delete_vpc"
```

create subnet

specify vpc id in inventories/dev/group_vars/all/settings.yml

run creating
```
ansible-playbook -i inventories/dev main.yml --connection=local --extra-vars "srv_group=localhost" --vault-password-file ~/.ansible/vaultfile --tags "create_subnet"
```

create EC2 instance
```
ansible-playbook -i inventories/dev main.yml --connection=local --extra-vars "srv_group=localhost" --vault-password-file ~/.ansible/vaultfile --tags "create_ec2_instance"
```

create S3 bucket
```
ansible-playbook -i inventories/dev main.yml --connection=local --extra-vars "srv_group=localhost" --vault-password-file ~/.ansible/vaultfile --tags "create_s3_bucket"
```

delete S3 bucket
```
ansible-playbook -i inventories/dev main.yml --connection=local --extra-vars "srv_group=localhost" --vault-password-file ~/.ansible/vaultfile --tags "delete_s3_bucket"
```