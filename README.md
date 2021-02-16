# Running-UiPath-with-Power-automate

///GET AUTHORIZATION CMD
POST
https://account.uipath.com/oauth/token
Content-Type          application/json
X-UIPATH-TenantName   YOUR TENANTNAME
///Body for the command
{
  "grant_type": "refresh_token",
  "client_id": "YOUR CLIENT ID FOR CLOUD ORCHESTRATOR",
  "refresh_token": "YOUR REFRESH TOKEN FOR CLOUD ORCHESTRATOR"
}

///Train code for parse JSON 
{
    "access_token": "test",
    "id_token": "test",
    "scope": "test",
    "expires_in": 86400,
    "token_type": "Bearer"
}

/// SEND START JOB CMD
https://platform.uipath.com/[Account Logical Name]/[Tenant Logical Name]/odata/Jobs/UiPath.Server.Configuration.OData.StartJobs
Content-Type          application/json
Bearer VariableFromAuthCMD
X-UIPATH-TenantName   YOUR TENANTNAME
X-UIPATH-OrganizationUnitId  YOUR TENANT ID

/// process Body For Modern Folder
{
  "startInfo": {
    "ReleaseKey": "YOUR PROCESS ReleaseKey",
    "RobotIds": [],
    "JobsCount": 1,
    "JobPriority": "Normal",
    "Strategy": "ModernJobsCount",
    "RuntimeType": "Unattended",
    "InputArguments": "{}"
  }
}

///Process with Parameters
 "InputArguments": "{\"param1\":\"P1\",\"param2\":\"P2\"}"
