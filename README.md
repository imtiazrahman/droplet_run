**do_run.yml playbook**

Create droplets in DO (image: Ubuntu 18.04, region: sgp1, size: s-1vcpu-1gb)

**Ansible Playbook for Creating DO Droplets* 

1. Open the do_run.yml file.
2. Check for the line *do_token* and *ssh_keys*.
3. In *do_token* put your DO API token and in *ssh_keys* put your ssh key id (see the **FIND YOUR SSH KEY ID using curl and DO API** section for finding the ssh key id). this key will be transfered to the droplets. which will be used by root.

**FIND YOUR SSH KEY ID using curl and DO API**
1. curl -X GET -H "Content-Type: application/json" -H "Authorization: Bearer **PUT_YOUR_DO_API_HERE**" "https://api.digitalocean.com/v2/account/keys"  | python -m json.tool
2. I use json.tool as a parser.

**RUN ANSIBLE PLAYBOOK**
1. Type the below command to run th playbook
2. **ansible-playbook -i inventory do_run.yml -u root**
