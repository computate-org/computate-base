# Publish the open source libraries

# :%s/4.1.8.a/4.1.8.b/g

cd ~/.local/src/computate-base
git add -i
git status
git commit
git push
git tag 4.1.8.12
git push --tags

cd ~/.local/src/computate-search
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.1.8.12
git push --tags

cd ~/.local/src/computate-vertx
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.1.8.12
git push --tags

cd ~/.local/src/computate
# Update version to 4.1.8.12 in pom.xml
git add -i
git status
git commit
git push
mvn clean install deploy -Pdeploy
git tag 4.1.8.12
git push --tags

cd ~/.local/src/computate-org
git add -i
git status
git commit
git push
git tag 4.1.8.12
git push --tags

