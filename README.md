# AnsibleChimorin
Ansible Playbooks for Windows machines

## Prerequistes

First run this command on your Windows Server machine via Powershell (as Administrator)

```powershell
iex(iwr https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1).Content
```

You can test connectivity to WinRM with the following command:

```bash
nc -w 3 -v <remote windows server ip/hostname> 5986
```

Also install the PYwinrm Python Module on the Ansible host.

```python
Pip install pywinrm
```

## Inventory file

```yml
[win]
<IP of Machine>

[win:vars]
ansible_connection=winrm 
ansible_user=<Admin User>
ansible_password=<Admin Password>
ansible_winrm_server_cert_validation=ignore
```