# Publish the open source libraries

cd ~/.local/src/computate-search
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.1.8.8
git push --tags

cd ~/.local/src/computate-vertx
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.1.8.8
git push --tags

cd ~/.local/src/computate
# Update version to 4.1.8.8 in pom.xml
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.1.8.8
git push --tags

