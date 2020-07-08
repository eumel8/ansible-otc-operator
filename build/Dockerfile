FROM quay.io/operator-framework/ansible-operator:v0.17.2

COPY requirements.yml ${HOME}/requirements.yml
COPY ansible-role-requirements.yml ${HOME}/ansible-role-requirements.yml
RUN ansible-galaxy role install -f -r ${HOME}/ansible-role-requirements.yml -p roles
RUN ansible-galaxy collection install -r ${HOME}/requirements.yml \
 && chmod -R ug+rwx ${HOME}/.ansible

COPY watches.yaml ${HOME}/watches.yaml

##COPY roles/ ${HOME}/roles/
COPY playbook.yml ${HOME}/playbook.yml
