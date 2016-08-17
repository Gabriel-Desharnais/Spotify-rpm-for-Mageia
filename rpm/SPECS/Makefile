name:=$(shell cat name)
release:=$(shell cat release)
version:=$(shell cat version)
arc:=$(shell cat arc)
nomDeTravail:=${name}-${version}-${release}.${arc}
pwd:=$(shell pwd)
ppd:=$(shell echo ${pwd} | sed -e s/\\/[^\\/]*$$//)
tarDir:=${ppd}/BUILDROOT/${nomDeTravail}/
lt:=$(shell echo -n "${tarDir}" | wc -c)
all: Spotify.spec ${ppd}/RPMS/${arc}/${nomDeTravail}.rpm

${ppd}/RPMS/${arc}/${nomDeTravail}.rpm: Spotify.spec
	@rpmbuild --target ${arc}  Spotify.spec

Spotify.spec: entete fichiers lsfichiers
	@cat entete>Spotify.spec
	@cat fichiers>>Spotify.spec
	@echo fait

lsfichiers:
	@echo %files>fichiers
	@echo %defattr\(-,root,root\)>>fichiers
	@find "${tarDir}" -type f | cut -c ${lt}-   >>fichiers


entete:name release version arc xentete
	@echo %define name ${name}>entete
	@echo %define version ${version}>>entete
	@echo %define release ${release}>>entete
	@cat xentete>>entete

init:
	@mkdir -p "${pwd}"/{BUILD,RPMS,SOURCES,SRPMS,SPECS,tmp}
	@mv name "${pwd}"/SPECS
	@mv release "${pwd}"/SPECS
	@mv version "${pwd}"/SPECS
	@mv arc "${pwd}"/SPECS
	@mkdir -p "${pwd}"/BUILDROOT
	@mv root "${pwd}"/BUILDROOT/root
	@mv "${pwd}"/BUILDROOT/root "${pwd}"/BUILDROOT/${nomDeTravail}
	@mv Makefile "${pwd}"/SPECS
	@echo "%_topdir                %(echo $HOME)/Programmation/Spotify rpm for Mageia/rpm"> ~/.rpmmacros
	@echo "%_tmppath               %(echo $HOME)/Programmation/Spotify rpm for Mageia/rpm/tmpbuild">>~/.rpmmacros
	@echo "%_signature             gpg">> ~/.rpmmacros
	@echo "%_gpg_name              Mageialinux">> ~/.rpmmacros
	@echo "%_gpg_path              ~/.gnupg">> ~/.rpmmacros
	@echo "%packager               jc">> ~/.rpmmacros
	@echo "%distributor            Mageia.org">> ~/.rpmmacros
