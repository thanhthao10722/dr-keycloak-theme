## How to install and enable theme

#### Prepare assets
Replace logo, and other assets file to `assets`. Copy it to equivelent location by running
```
$ scripts/x-copy-assets
```

#### Install
Copy this directory to `themes` directory of keycloak deployment

#### Enbable in the Administration Console

1. Login -> Realm Setting -> Themes
2. Edit `standalone.xml` and add welcome theme entry `<welcomeTheme>tifl-keycloak-theme</welcomeTheme>`

```
            <theme>
                ...
                <welcomeTheme>tifl</welcomeTheme>
            </theme>
```
3. Restart if needed


## Tip on develop themes

1. Download the release from `keycloak` website, extract and run standalone script.
2. Start develop inside `themes` directory
3. Disbale cache to enable reload reflect the changes

Edit `/standalone/configuration/standalone.xml`. Change to following setting
```
            <theme>
                <staticMaxAge>-1</staticMaxAge>
                <cacheThemes>false</cacheThemes>
                <cacheTemplates>false</cacheTemplates>
                <dir>${jboss.home.dir}/themes</dir>
                <welcomeTheme>tifl</welcomeTheme>
            </theme>
```
4. Restart
To reload server. Go to `bin`

```
$ ./jboss-cli.sh
> connect
> reload
```
