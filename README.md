# Changelog
## 0.4.1
### Changes
- Added documentation for the values file and link in the notes.txt
- Mariadb can now receive a different username other than root
### Fix
- Removed unused maps in values file
## 0.4.0
### Changes
- Upgraded deno default tag from 1.3.1 to 1.5.1
- Webserver use secret to override default values inside the container
- Webserver has now livenessProbe and init-containers, probe can be override in values file
- Re-added namespaces 
- By default now, name of the ressources will use .Release.Name 
- env var for db connection will now use a secret
- Added a readinessProbe for Mariadb
- by default now, the number of replicas for the webserver will be set to 3 in the values.yaml
- Can now release multiple release with the default version
### Fix
- Deno persistentVolume uses ClaimRef to assure the connection with the good PersistentVolumeClaim, and added the same with VolumeName for PersitentVolumeClaim ( in some cases it would connect to the mariadb PersitentVolume and cause mariadb to fail )
## 0.3.0
### This tag added nothing, was a missplay from us
## 0.2.0
### Changes
- Pass mariadb from a Deployment to a StatefulSet, deleted pvc in consequences
## 0.1.0
### Changes 
- Using 1.3.1 tag by default for deno-webserver, latest for mariadb
- Added deployment, pv, pvc, service and ingress for deno-webserver 
- Added deployment, pv, pvc, service and ingress for mariadb
- Generated values.yaml file
