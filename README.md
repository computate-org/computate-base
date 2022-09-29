# Publish the open source libraries

# :%s/4.2.5.a/4.2.5.b/g

# Update version of computate-base/pom.xml
# Copy the properties from computate-base/pom.xml to computate/pom.xml
# Copy the properties from computate-base/pom.xml to computate-org/roles/computate_project_file_enUS/templates/java/pom.xml

cd ~/.local/src/computate-base
mvn clean install
git add -i
git status
git commit
git push
git tag 4.2.5.14
git push --tags

cd ~/.local/src/computate-search
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.2.5.14
git push --tags

cd ~/.local/src/computate-vertx
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.2.5.14
git push --tags

cd ~/.local/src/computate
# Update version to 4.2.5.14 in pom.xml
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.2.5.14
git push --tags

cd ~/.local/src/computate-org
git add -i
git status
git commit
git push
git tag 4.2.5.14
git push --tags

