# ansible-inventory-perfsonar-umich-core

ansible ps_archive \
  --inventory ../ansible-inventory-perfsonar-umich-core/inventory \
  --ask-pass \
  --ask-become-pass \
  --become \
  --become-method sudo \
  --become-user root \
  -m ping

ansible-playbook \
  --limit ps_archive \
  --inventory ../ansible-inventory-perfsonar-umich-core/inventory \
  --ask-pass \
  --ask-become-pass \
  --become \
  --become-method sudo \
  --become-user root \
  perfsonar.yml

ansible-playbook \
  --limit ps_archive \
  --inventory ../ansible-inventory-perfsonar-umich-core/inventory \
  --ask-pass \
  --ask-become-pass \
  --become \
  --become-method sudo \
  --become-user root \
  --tags config \
  perfsonar.yml

ansible-playbook \
  --limit ps_grafana \
  --inventory ../ansible-inventory-perfsonar-umich-core/inventory \
  --ask-pass \
  --ask-become-pass \
  --become \
  --become-method sudo \
  --become-user root \
  perfsonar.yml

ansible ps_testpoint \
  --inventory ../ansible-inventory-perfsonar-umich-core/inventory \
  --ask-become-pass \
  --become \
  --become-method su \
  --become-user root \
  -m ping


ansible ps_testpoint \
  --inventory ../ansible-inventory-perfsonar-umich-core/inventory \
  --ask-become-pass \
  --become \
  --become-method su \
  --become-user root \
  -a "hostname"

ansible ps_testpoint \
  --inventory ../ansible-inventory-perfsonar-umich-core/inventory \
  --ask-become-pass \
  --become \
  --become-method su \
  --become-user root \
  -a "psconfig remote add \"https://raw.githubusercontent.com/UMNET-perfSONAR/ansible-inventory-perfsonar-umich-core/main/psconfig_meshes/core_mesh.json\""


ansible ps_archive \
  --inventory ../ansible-inventory-perfsonar-umich-core/inventory \
  --ask-pass \
  --ask-become-pass \
  --become \
  --become-method sudo \
  --become-user root \
  -a "psconfig remote add \"https://raw.githubusercontent.com/UMNET-perfSONAR/ansible-inventory-perfsonar-umich-core/main/psconfig_meshes/core_mesh.json\""

