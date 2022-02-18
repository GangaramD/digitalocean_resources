# digitalocean_resources
ansible to create resource on digital ocean

# Requirement
ansible:
    `version: 2.7`

Python:
 `version: python2.7`
 
 Pip:
   `version:>= 20.3.4`
   `pip -V
    pip 20.3.4 from /home/$user/.local/lib/python2.7/site-packages/pip (python 2.7)`
 
 dopy: 
  `version: dopy>=0.3.5,<=0.3.5`
      `sudo pip install 'dopy>=0.3.5,<=0.3.5'` 

do_community_module:
   `ansible-galaxy collection install community.digitalocean`
   https://docs.ansible.com/ansible/latest/collections/community/digitalocean/index.html#plugin-index

# Export DO_API_TOKEN 
   `export DO_API_TOOKEN=1111TokenValue22222`

# Create Droplet API ref
https://docs.digitalocean.com/reference/api/api-reference/#operation/create_droplet

# Size_id
https://docs.digitalocean.com/reference/api/api-reference/#operation/list_all_sizes 

example:
`"sizes": [
    "s-1vcpu-1gb",
    "s-1vcpu-2gb",
    "s-1vcpu-3gb",
    "s-2vcpu-2gb",
    "s-3vcpu-1gb",
    "s-2vcpu-4gb",
    "s-4vcpu-8gb",
    "s-6vcpu-16gb",
    "s-8vcpu-32gb",
    "s-12vcpu-48gb",
    "s-16vcpu-64gb",
    "s-20vcpu-96gb",
    "s-24vcpu-128gb",
    "s-32vcpu-192g"]`

# region_id
https://docs.digitalocean.com/reference/api/api-reference/#operation/list_all_regions 

example: 
   `"regions": [
    "ams2",
    "ams3",
    "blr1",
    "fra1",
    "lon1",
    "nyc1",
    "nyc2",
    "nyc3",
    "sfo1",
    "sfo2",
    "sfo3",
    "sgp1",
    "tor1"
]  `


# Run ansible
`ansible-playbook -i inventory/dev/invn.yaml do_droplet_creation.yaml -v`

# Specific tag
`ansible-playbook -i inventory/dev/invn.yaml do_droplet_volume.yaml --tags create-storage -vv`

`ansible-playbook -i inventory/dev/invn.yaml do_droplet_volume.yaml --tags resize-storage -vv`

`ansible-playbook -i inventory/dev/invn.yaml do_droplet_volume.yaml --tags attach-storage -vv`

`ansible-playbook -i inventory/dev/invn.yaml do_droplet_volume.yaml --tags detach-storage -vv`

`ansible-playbook -i inventory/dev/invn.yaml do_droplet_volume.yaml --tags delete-storage -vv`

# Community Digital Ocean Module references

https://docs.ansible.com/ansible/latest/collections/community/digitalocean/index.html#plugin-index

