``` PowerShell
# Azure Subscription I want to use
$subscriptionId = "xxxx-xxxx-xxxx-xxxx"

# Select the right Azure subscription
Set-AzContext -Subscription $subscriptionId

# Get all Azure VMs in the subscription with their statuses
$allAzureVMs = Get-AzVM -status | Where-Object {
    $_.PowerState -eq "VM running" -and $_.StorageProfile.OSDisk.OSType -eq "Windows"
}

# Run the script on all VMs in parallel
$allAzureVMs | ForEach-Object -Parallel {
    $out = Invoke-AzVMRunCommand `
        -ResourceGroupName $_.ResourceGroupName ` # Use the ResourceGroupName from each VM
        -Name $_.Name `
        -CommandId 'RunPowerShellScript' `
        -ScriptPath .\test.ps1 

    # Format the output with the VM name
    $output = $_.Name + " " + $out.Value[0].Message
    $output
} ``` 
