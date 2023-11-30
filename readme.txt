git grep "result_path" $(git rev-list --all)


$result = ''; git grep "result_path" $(git rev-list --all) | ForEach-Object { $_ -split "`r?`n" } | ForEach-Object { $_.Split(":")[0] } | ForEach-Object { $result += $_ + ' ' }; "git log --no-walk --oneline " + $result | powershell

