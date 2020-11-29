# binary-build
We will deploy already generated war file on Jboss EAP
### clone your repo to local folder ##
git clone https://github.com/wael2000/binary-build.git
### move to the binaries folder ###
cd binary-build
### create build config ###
oc new-build --image-stream=jboss-eap64-openshift:1.4 --binary=true --name=warbuild
### start the build ###
oc start-build warbuild --from-dir=.
## once image is creatd, create a new app base on this image ##
oc new-app warbuild
## create the route to expose the svc ##
