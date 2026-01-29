@"
`$fedauth = Read-Host "Paste FedAuth cookie value and press Enter"
`$rtfa = Read-Host "Paste rtFa cookie value and press Enter"

`$envContent = Get-Content .env
`$envContent = `$envContent -replace 'FEDAUTH_COOKIE=.*', "FEDAUTH_COOKIE=`$fedauth"
`$envContent = `$envContent -replace 'RTFA_COOKIE=.*', "RTFA_COOKIE=`$rtfa"
`$envContent | Set-Content .env

Write-Host "Cookies updated successfully!" -ForegroundColor Green
"@ | Out-File update_cookies.ps1
