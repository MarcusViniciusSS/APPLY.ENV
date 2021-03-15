# Instalação

## Primeiro passo:
 - Baixar [powershell](https://docs.microsoft.com/pt-br/powershell/scripting/whats-new/what-s-new-in-powershell-70?view=powershell-7.1).
 - Baixa a fonte NF Hack [nerd-fonts](https://github.com/ryanoasis/nerd-fonts/blob/master/patched-fonts/Hack/Regular/complete/Hack%20Regular%20Nerd%20Font%20Complete%20Mono%20Windows%20Compatible.ttf)

## Segundo Passo
   - Criar um arquivo em: "C:\Users\ [seuusuario] \Documents\PowerShell"
   - Adicionar o Arquivo: Microsoft.PowerShell_profile.ps1 com as configurações abaixo.
```powershell
Set-ExecutionPolicy Unrestricted
Install-Module PSReadLine -Force -Scope CurrentUser -AllowPrerelease
Install-Module posh-git -Force -Scope CurrentUser -AllowPrerelease
Install-Module oh-my-posh -Force -Scope CurrentUser -AllowPrerelease
Import-Module posh-git
Import-Module oh-my-posh

Set-PoshPrompt -Theme slim

# this will override your current profile, so if you have something custom, do not execute it.
$sb = New-Object -TypeName System.Text.StringBuilder
$sb.AppendLine("Import-Module posh-git");
$sb.AppendLine("Import-Module oh-my-posh");
$sb.AppendLine("Set-PoshPrompt -Theme slim");
$sb.AppendLine("Set-PSReadlineKeyHandler -Key Tab -Function MenuComplete");
$sb.AppendLine("Set-PSReadLineOption -PredictionSource History");

$sb.ToString() | Out-File -FilePath $profile
```

## Ultimo Passo
    - Abra o terminal como administrador para instalar todos os pacotes, quando termina de instalar abra novamente e seu terminal ficará assim.
![image](https://ohmyposh.dev/assets/images/agnoster-2554ec80c8f34ce54a7dac6c1a2f111a.png)



Feito por **Marcus Vinicius(Lowpoc/olasoumarcus)**!
