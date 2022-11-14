# Publish the open source libraries

# :%s/4.3.3.a/4.3.3.b/g

# Update version of computate-base/pom.xml
# Copy the properties from computate-base/pom.xml to computate/pom.xml
# Copy the properties from computate-base/pom.xml to computate-upgrade/roles/computate_project_file_enUS/templates/java/pom.xml
# Update the computate.version to 4.3.3.17 in ../computate-upgrade/roles/computate_project_file_enUS/templates/java/pom.xml
# Update version to 4.3.3.17 in ../computate/pom.xml
# Add release notes based on a compare: https://github.com/computate-org/computate-base/compare/4.3.3.x...main

cd ~/.local/src/computate-base
git add -i
git commit
git push
git status
mvn clean install deploy -Pdeploy
git tag 4.3.3.17
git push --tags

cd ~/.local/src/computate-search
# Add release notes based on a compare: https://github.com/computate-org/computate-search/compare/4.3.3.x...main
vim release/4.3.3.17-release-notes.md
git add -i
git commit -m "Releasing version 4.3.3.17"
git push
git status
mvn clean install deploy -Pdeploy
git tag 4.3.3.17
git push --tags

cd ~/.local/src/computate-vertx
# Add release notes based on a compare: https://github.com/computate-org/computate-vertx/compare/4.3.3.x...main
vim release/4.3.3.17-release-notes.md
git add -i
git commit -m "Releasing version 4.3.3.17"
git push
git status
mvn clean install deploy -Pdeploy
git tag 4.3.3.17
git push --tags

cd ~/.local/src/computate
# Add release notes based on a compare: https://github.com/computate-org/computate/compare/4.3.3.x...main
vim release/4.3.3.17-release-notes.md
git add -i
git commit -m "Releasing version 4.3.3.17"
git push
git status
mvn clean install deploy -Pdeploy
git tag 4.3.3.17
git push --tags

