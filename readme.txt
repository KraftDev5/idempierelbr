### TO BUILD ON MAVEN ###

mvn verify -Didempiere.target=org.idempierelbr.p2.targetplatform

### TO CONFIGURE IN A DIFFERENT SERVER OR FOLDER ###

# NOTE: Compilation is configured for jenkins server at ci.idempiere.org
# if needed to compile locally or in a different server setup you need to change relativePath in all pom.xml files
# and the repository location in target platform file

### TO INSTALL WITH update-prd.sh ###

install product org.idempierelbr.feature.feature.group

### TO INSTALL JAR FILES IN LOCAL REPOSITORY ###

# Install fixedformat4j-1.3.4.jar copied in /tmp folder
mvn \
  deploy:deploy-file \
  -DgroupId=local.fixedformat4j \
  -DartifactId=fixedformat4j \
  -Dversion=1.3.4 \
  -Durl=file:./local-maven-repo/ \
  -Dpackaging=jar \
  -DrepositoryId=local-maven-repo \
  -DupdateReleaseInfo=true \
  -Dfile=/tmp/fixedformat4j-1.3.4.jar \
  -Didempiere.target=org.idempierelbr.p2.targetplatform

# Install DSGEBrazilUtils.jar copied in /tmp folder
mvn \
  deploy:deploy-file \
  -DgroupId=local.DSGEBrazilUtils \
  -DartifactId=DSGEBrazilUtils \
  -Dversion=NOT_INFORMED \
  -Durl=file:./local-maven-repo/ \
  -Dpackaging=jar \
  -DrepositoryId=local-maven-repo \
  -DupdateReleaseInfo=true \
  -Dfile=/tmp/DSGEBrazilUtils.jar \
  -Didempiere.target=org.idempierelbr.p2.targetplatform
