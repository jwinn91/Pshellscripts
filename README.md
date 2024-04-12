<h2>Powershell Scripts</h2>

Adding a clinet to your domain and changing the PC name:
Invoke-Command -ScriptBlock {
    $LocalCredential = Get-Credential -Message "Enter Local Administrator Credentials"
    Rename-Computer -NewName "Win10" -LocalCredential $LocalCredential -Force ;
    $DomainCredential = Get-Credential -Message "Enter Domain Credentials"
    Add-Computer -DomainName "cyberlab.com" -Credential $DomainCredential -Restart
}

