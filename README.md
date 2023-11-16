# Publish the open source libraries

Run the following Ansible playbook to begin the new release: 

```bash
ansible-playbook computate_new_release.yml
```

The run will fail, but it will tell you what the next release number will be. Run the playbook again with the desired release version specified: 


```bash
ansible-playbook computate_new_release.yml -e NEXT_VERSION=4.4.4.1
```

# :%s/4.2.7.a/4.2.7.b/g

# Update version of computate-base/pom.xml
# Copy the properties from computate-base/pom.xml to computate/pom.xml
# Copy the properties from computate-base/pom.xml to computate-upgrade/roles/computate_project_file_enUS/templates/java/pom.xml
# Update the computate.version to 4.4.4.0 in ../computate-upgrade/roles/computate_project_file_enUS/templates/java/pom.xml
# Update computate.version property to 4.4.4.0 in ../computate/pom.xml
# Update version to 4.4.4.0 in ../computate/pom.xml
# Update computate parent version property to 4.4.4.0 in ../computate-search/pom.xml
# Update version to 4.4.4.0 in ../computate-search/pom.xml
# Update computate parent version property to 4.4.4.0 in ../computate-vertx/pom.xml
# Update computate-search version property to 4.4.4.0 in ../computate-vertx/pom.xml
# Update version to 4.4.4.0 in ../computate-vertx/pom.xml

cd ~/.local/src/computate-base
git add -i
git commit -m "Releasing version 4.4.4.0"
git push
git status
mvn clean install deploy -Pdeploy
git tag 4.4.4.0
git push --tags
# Create release from tag: https://github.com/computate-org/computate-base/releases/tag/4.4.4.0

cd ~/.local/src/computate-search
# Update computate parent version and artifact version to 4.4.4.0: vim pom.xml
# Update version to 4.4.4.0 in pom.xml
git add -i
git commit -m "Releasing version 4.4.4.0"
git push
git status
mvn clean install deploy -Pdeploy
git tag 4.4.4.0
git push --tags
# Create release from tag: https://github.com/computate-org/computate-search/releases/tag/4.4.4.0

cd ~/.local/src/computate-vertx
# Update computate parent version, artifact version and computate-search version to 4.4.4.0: vim pom.xml
# Update computate-search version property to 4.4.4.0 in pom.xml
# Update version to 4.4.4.0 in pom.xml
git add -i
git commit -m "Releasing version 4.4.4.0"
git push
git status
mvn clean install deploy -Pdeploy
git tag 4.4.4.0
git push --tags
# Create release from tag: https://github.com/computate-org/computate-vertx/releases/tag/4.4.4.0

cd ~/.local/src/computate
# Update computate.version to 4.4.4.0: vim pom.xml
# Update version to 4.4.4.0 in pom.xml
git add -i
git commit -m "Releasing version 4.4.4.0"
git push
git status
mvn clean install deploy -Pdeploy
git tag 4.4.4.0
git push --tags
# Create release from tag: https://github.com/computate-org/computate/releases/tag/4.4.4.0

