# Tiendeo DevOps Playground
Start the containers by running the following snippet in your terminal :

```bash
docker-compose build # Build the containers
docker-compose up # Start the containers
```
The containers ansible, web and db are now running the background

⚠ In a second terminal, run this second snippet to access the ansible-enabled container (named as "ansible" within the network) 

```bash
docker exec -it devops-playground_ansible_1 /bin/bash
```

Then you can try to ssh into the others containers (such as web or db) with the following snippets

```bash
ssh web
```

You can add/modify playbooks inside the shared-folder of this repository, it's a volume that's mounted at /shared-folder in the ansible container. This folder should be your workplace, place your inventory, templates etc in it and run your playbooks from it.
```bash
cd /shared-folder
ansible-playbook playbook.yml -i inventory.ini
```

---

If you do any change to the Dockerfiles, don't forget to build the containers again
```bash
docker-compose build
```
