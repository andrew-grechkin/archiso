$(HOME)/git:
	@mkdir -p ~/git

$(HOME)/git/ansible-arch: $(HOME)/git
	@git clone https://github.com/andrew-grechkin/ansible-arch.git git/ansible-arch

# => -------------------------------------------------------------------------------------------------------------- {{{1

.ONESHELL:
.PHONY = install update-playbook

install: update-playbook
	@lsblk
	@echo "Starting installation..."
	@echo
	@cd git/ansible-arch && ansible-playbook -i localhost-not-ready.yaml playbooks/arch-install-os.yaml

update-playbook: $(HOME)/git/ansible-arch
	@git -C git/ansible-arch pull
