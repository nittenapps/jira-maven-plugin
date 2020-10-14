# Maven JIRA Plugin
Collection of maven goals to work with the JIRA Cloud platform, by using the
[JIRA REST API v3](https://developer.atlassian.com/cloud/jira/platform/rest/v3/).

This plugin is based on the [maven-changes-plugin](http://maven.apache.org/plugins/maven-changes-plugin/) plugin,
addressing the cloud platform authentication, and using the version 3 of the JIRA REST API.

## Usage
This project acts as a regular reporting plugin, so you only need to add it to your reporting plugins list.

```xml
<project>
  ...
    <reporting>
      <plugins>
        <plugin>
          <groupId>dev.nittenapps.maven.plugins</groupId>
          <artifactId>jira-maven-plugin</artifactId>
          <version>${jira-maven-plugin.version}</version>
          <configuration>
            <onlyCurrentVersion>true</onlyCurrentVersion>
          </configuration>
        </plugin>
      </plugins>
    </reporting>
  ...
</project>
```

In order to authenticate to your JIRA Cloud account this plugin uses the server configuration in the Maven settings
file, you just need to create an API Token, and supply it as the password of your JIRA account.

```xml
<settings>
  ...
    <server>
      <id>jira</id>
      <username>${jira.user}</username>
      <password>${jira.apiToken}</password>
    </server>
  ...
</settings>
```

## Contributing
Any contribution to this project is very welcome.

You can use the [Issue list](https://github.com/nittenapps/jira-maven-plugin/issues) in order to send your feedback and
suggestions.

In order to contribute, I suggest you to use [git-flow (AVH Edition)](https://github.com/petervanderdoes/gitflow-avh),
forking this repo in your own Github account, and following these steps on your local installation:

### Clone the repository

```shell
git clone -b main git@github.com:<username>/jira-maven-plugin.git
```

Note the `-b main` argument, it is required to clone the `main` branch, and not the `develop` branch, which is the
default branch in this repo.

### Initialize git-flow
After that initialize the local git-flow repository

```shell
git flow init -d
```

### Code your feature
Before start coding your new feature run

```shell
git flow feature start <your feature>
```

Now you can start coding and committing your work.

### Publish your new feature
When your done with the new feature publish it to your fork

```shell
git flow feature publish <your feature>
```

### Open a pull request

Then open a pull request to your feature branch.
