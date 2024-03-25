# choco frequent commands


choco list --local-only

choco config

choco config get cacheLocation
choco config get --name cacheLocation
choco config set cacheLocation V:\choco_temp
choco config set --name cacheLocation --value V:\choco_temp

choco config unset proxy
choco config unset --name proxy


Import-Module PowerShellGet
Register-PSRepository -Name "scriptcsnightly" -SourceLocation "https://www.myget.org/F/scriptcsnightly/api/v2"
Install-Module -Name "scriptcs" -RequiredVersion "0.17.1" -Repository "scriptcsnightly"
