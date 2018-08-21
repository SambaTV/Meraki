Every day auto delete files modified older than 7 days

     * * * * *  /usr/local/bin/pwsh /Users/rodneynobles/Backup/JumpCloudCSVBackup.ps1 &>/tmp/JCBackup.log
    @daily find '/Users/rodneynobles/Backup/JCBackup' -mtime +6 -type f -delete



