name:=$(shell cat name)
release:=$(shell cat release)
version:=$(shell cat version)
arc:=$(shell cat arc)
nomDeTravail:=${name}-${version}-${release}.${arc}
pwd:=$(shell pwd)
ppd:=$(shell echo ${pwd} | sed -e s/\\/[^\\/]*$$//)
tarDir:=${ppd}/BUILDROOT/${nomDeTravail}/
lt:=$(shell echo -n "${tarDir}" | wc -c)
all: Spotify.spec
	
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
	
