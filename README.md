# JsonToEnv

Monitor a folder for JSON files and update contents of an ENV file

The initial use case is for AWS SSO Logins on Windows.

- Monitor a folder `c:\users\[username]\.aws\cli\cache` for changed files, e.g. [guid].json
- Open the changed [guid].json file and parse it
- Open the .env file and create or replace the mapped entries, see settings.json below.

Example `settings.json`

```
{
  folder: "c:/users/[username]/.aws/cli/cache",
  envfile: "c:/projects/myproject/.env",
  mapping: [
    AccessKeyId: "AWS_ACCESS_KEY_ID",
    SecretAccessKey: "AWS_SECRET_ACCESS_KEY",
    SessionToken: "AWS_SESSION_TOKEN"
  ]
}
```
