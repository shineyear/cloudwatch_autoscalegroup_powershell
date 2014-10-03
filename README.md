cloudwatch_autoscalegroup_powershell
====================================

support cloudwatch custom metrics work with beanstalk auto scale group on windows powershell script


because the aws cloudwatch powershell script can not support merge metrics to auto scale group, 

so when you use beanstalk with windows instance , the auto scale group and monitor, alarm will not work well, 

so i change the script to fetch the instance auto scale group name , then set it when you put metrics back to cloudwatch.

useage:

powershell.exe -ExecutionPolicy Unrestricted .\AmazonCloudWatchMonitoringWindows\mon-put-metrics-mem.ps1 -aws_credential_file monitoring_creds.conf -mem_util -mem_avail -auto_scale > metrics.log 2>&1

powershell.exe -ExecutionPolicy Unrestricted .\AmazonCloudWatchMonitoringWindows\mon-put-metrics-disk.ps1 -aws_credential_file monitoring_creds.conf -disk_drive C:,D: -disk_space_util -disk_space_avail -auto_scale > metrics.log 2>&1

steps:

replace this 2 file in your AmazonCloudWatchMonitoringWindows folder

