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
