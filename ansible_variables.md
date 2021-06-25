

## ansible varibles

https://docs.ansible.com/ansible/latest/user_guide/playbooks_variables.html#ansible-variable-precedence

1. command line values (for example, -u my_user, these are not variables)

2. role defaults (defined in role/defaults/main.yml) 1

3. inventory file or script group vars 2

4. inventory group_vars/all 3

5. playbook group_vars/all 3

6. inventory group_vars/* 3

7. playbook group_vars/* 3

8. inventory file or script host vars 2

9. inventory host_vars/* 3

10. playbook host_vars/* 3

11. host facts / cached set_facts 4

12. play vars

13. play vars_prompt

14. play vars_files

15. role vars (defined in role/vars/main.yml)

16. block vars (only for tasks in block)

17. task vars (only for the task)

18. include_vars

19. set_facts / registered vars

20. role (and include_role) params

21. include params

22. extra vars (for example, -e "user=my_user")(always win precedence)


## highest precedence is extra vars
ex :
---
ansible-playbook -i hosts -e package_name=tree lamp.yml
---

In majority of Cases variables are defined
In Playbook 
In Inventory
In Inventory group_vars and host_vars
set fact
Roles
extra vars
