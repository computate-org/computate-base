# Publish the open source libraries

# :%s/4.2.5.a/4.2.5.b/g

# Update version of computate-base/pom.xml
# Copy the properties from computate-base/pom.xml to computate/pom.xml
# Copy the properties from computate-base/pom.xml to computate-upgrade/roles/computate_project_file_enUS/templates/java/pom.xml
# Update the computate.version to 4.2.5.16 in computate-upgrade/roles/computate_project_file_enUS/templates/java/pom.xml
# Update version to 4.2.5.16 in computate/pom.xml

cd ~/.local/src/computate-base
mvn clean install
git add -i
git status
git commit
git push
git tag 4.2.5.16
git push --tags

cd ~/.local/src/computate-search
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.2.5.16
git push --tags

cd ~/.local/src/computate-vertx
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.2.5.16
git push --tags

cd ~/.local/src/computate
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.2.5.16
git push --tags

cd ~/.local/src/computate-upgrade
git add -i
git status
git commit
git push
git tag 4.2.5.16
git push --tags

