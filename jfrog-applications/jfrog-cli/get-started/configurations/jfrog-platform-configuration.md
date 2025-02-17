# JFrog Platform Configuration

**Adding and Editing Configured Servers**

The **config add** and **config edit** commands are used to add and edit JFrog Platform server configuration, stored in JFrog CLI's configuration storage. These configured servers can be used by the other commands. The configured servers' details can be overridden per command by passing in alternative values for the URL and login credentials. The values configured are saved in file under the JFrog CLI home directory.

|                        |                                                                                                                                                                                                                                                                                                                                                                                                    |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Command Name           | Config Add/ Config Edit                                                                                                                                                                                                                                                                                                                                                                            |
| Abbreviation           | c add / c edit                                                                                                                                                                                                                                                                                                                                                                                     |
| Command options        |                                                                                                                                                                                                                                                                                                                                                                                                    |
| --access-token         | <p>[Optional]</p><p>Access token.</p>                                                                                                                                                                                                                                                                                                                                                              |
| --artifactory-url      | <p>[Optional]</p><p>Artifactory URL.</p>                                                                                                                                                                                                                                                                                                                                                           |
| --basic-auth-only      | <p>[Default: false]</p><p>Used for Artifactory authentication. Set to true to disable replacing username and password/API key with automatically created access token that's refreshed hourly. Username and password/API key will still be used with commands which use external tools or the JFrog Distribution service. Can only be passed along with username and password/API key options.</p> |
| --client-cert-key-path | <p>[Optional]</p><p>Private key file for the client certificate in PEM format.</p>                                                                                                                                                                                                                                                                                                                 |
| --client-cert-path     | <p>[Optional]</p><p>Client certificate file in PEM format.</p>                                                                                                                                                                                                                                                                                                                                     |
| --dist-url             | <p>[Optional]</p><p>Distribution URL.</p>                                                                                                                                                                                                                                                                                                                                                          |
| --enc-password         | <p>[Default: true]<br><br>If true, the configured password will be encrypted using Artifactory's<a href="https://www.jfrog.com/confluence/display/RTF/Artifactory+REST+API#ArtifactoryRESTAPI-GetUserEncryptedPassword">encryption API</a> before being stored. If false, the configured password will not be encrypted.</p>                                                                       |
| --insecure-tls         | <p>[Default: false]</p><p>Set to true to skip TLS certificates verification, while encrypting the Artifactory password during the config process.</p>                                                                                                                                                                                                                                              |
| --interactive          | <p>[Default: true, unless $CI is true]</p><p>Set to false if you do not want the config command to be interactive.</p>                                                                                                                                                                                                                                                                             |
| --mission-control-url  | <p>[Optional]</p><p>Mission Control URL.</p>                                                                                                                                                                                                                                                                                                                                                       |
| --password             | <p>[Optional]</p><p>JFrog Platform password.</p>                                                                                                                                                                                                                                                                                                                                                   |
| --pipelines-url        | <p>[Optional]</p><p>Pipelines URL.</p>                                                                                                                                                                                                                                                                                                                                                             |
| --ssh-key-path         | <p>[Optional]</p><p>For authentication with Artifactory. SSH key file path.</p>                                                                                                                                                                                                                                                                                                                    |
| --url                  | <p>[Optional]</p><p>JFrog platform URL.</p>                                                                                                                                                                                                                                                                                                                                                        |
| --user                 | <p>[Optional]</p><p>JFrog Platform username.</p>                                                                                                                                                                                                                                                                                                                                                   |
| --xray-url             | \[Optional] Xray URL.                                                                                                                                                                                                                                                                                                                                                                              |
| --overwrite            | <p>[Available for <em>config add</em> only]<br><br>[Default: false]<br><br>Overwrites the instance configuration if an instance with the same ID already exists.</p>                                                                                                                                                                                                                               |
| Command arguments      |                                                                                                                                                                                                                                                                                                                                                                                                    |
| server ID              | A unique ID for the server configuration.                                                                                                                                                                                                                                                                                                                                                          |

**Removing Configured Servers**

The _config remove_ command is used to remove JFrog Platform server configuration, stored in JFrog CLI's configuration storage.

|                   |                                                                                      |
| ----------------- | ------------------------------------------------------------------------------------ |
| Command name      | config remove                                                                        |
| Abbreviation      | c rm                                                                                 |
| Command options   |                                                                                      |
| --quiet           | <p>[Default: $CI]</p><p>Set to true to skip the delete confirmation message.</p>     |
| Command arguments |                                                                                      |
| server ID         | The server ID to remove. If no argument is sent, all configured servers are removed. |

**Showing the Configured Servers**

The _config show_ command shows the stored configuration. You may show a specific server's configuration by sending its ID as an argument to the command.

|                   |                                                                                         |
| ----------------- | --------------------------------------------------------------------------------------- |
| Command name      | config show                                                                             |
| Abbreviation      | c s                                                                                     |
| Command arguments |                                                                                         |
| server ID         | The ID of the server to show. If no argument is sent, all configured servers are shown. |

**Setting a Server as Default**

The _config use_ command sets a configured server as default. The following commands will use this server.

|                   |                                         |
| ----------------- | --------------------------------------- |
| Command name      | config use                              |
| Command arguments |                                         |
| server ID         | The ID of the server to set as default. |

**Exporting and Importing Configuration**

The _config export_ command generates a token, which stores the server configuration. This token can be used by the _config import_ command, to import the configuration stored in the token, and save it in JFrog CLI's configuration storage.

**Export**

|                   |                                |
| ----------------- | ------------------------------ |
| Command name      | config export                  |
| Abbreviation      | c ex                           |
| Command arguments |                                |
| server ID         | The ID of the server to export |

**Import**

|                   |                     |
| ----------------- | ------------------- |
| Command name      | config import       |
| Abbreviation      | c im                |
| Command arguments |                     |
| server token      | The token to import |
