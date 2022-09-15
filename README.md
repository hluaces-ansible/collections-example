# Requisitos

- Ansible a una versión moderna (2.10+)
- Git
- SSH

# Cómo usar

- Clona este repo
- Instala las dependencias de colecciones remotas:

    ```
    ansible-galaxy collection install -r collections/requirements.yml -p collections/vendors
    ansible-galaxy role install -r roles/requirements.yml -p roles/vendors
    ```

- Ejecuta el playbook local para ver un rol de colección en acción:

    ```
    ansible-playbook -vv -i inventory/default.ini playbooks/hello_world.yml
    ```

# ¿Cómo funciona?

- Define requisitos de roles y colecciones en:
    - `collections/requirements.yml`
    - `roles/requirements.yml`
- Dile a Ansible que busque en las carpetas de este repositorio las colecciones. Para ello, ver en `ansible.cfg` las directivas:
    - `collections_paths`
    - `roles_paths`
- Instala las dependencias con los comandos de la sección anterior
- Usa los roles (¡o Playbooks!) de tus colecciones usando su namespace, p.ej.: `hluaces.${NOMBRE DE COLECCIÓN}.${NOMBRE DE ROL}`

# Otros recursos

- [Plantilla de colección](https://github.com/hluaces-ansible/collection-template)
- [Plantilla de rol](https://github.com/hluaces-ansible/role-template)
- [Documentación oficial de colecciones](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html)
- [Formato del fichero `requirements.yml`](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html)
