# Azure Storage & Secure File Access

## Project Overview
This project demonstrates how to store files securely using Azure Blob Storage and provide temporary, controlled access through Shared Access Signatures (SAS).

## Objectives
- Store files in Azure Blob Storage.
- Configure private container access.
- Prevent anonymous public access.
- Generate a read-only SAS URL.
- Validate authorized and unauthorized access.

## Azure Resources
- **Storage Account:** Existing Azure Storage account
- **Container:** `mycontainer`
- **Blob:** `IRON THRONE.png`
- **Security:** Anonymous access disabled; container set to Private
- **Access Method:** SAS URL with read-only permission and HTTPS

## Architecture & Data Flow
1. A file is stored in an Azure Blob Storage container.
2. The storage account blocks anonymous public access.
3. A time-limited SAS URL grants read access to the selected blob.
4. The SAS URL is tested in an Incognito browser window.
5. The normal Blob URL is tested without SAS authorization.

## Validation Results

| Test | Expected Result | Outcome |
|---|---|---|
| SAS URL with valid permissions | File opens | Passed |
| Normal Blob URL without SAS | Access denied | Passed |
| Container public access | Private | Verified |

The normal Blob URL returned `PublicAccessNotPermitted`, confirming that anonymous access was blocked.

## Key Learnings
- Azure Blob Storage and containers
- Anonymous access controls
- Shared Access Signatures (SAS)
- Read-only and time-limited access
- Secure cloud file storage validation

## Security Notes
- SAS URLs are sensitive bearer credentials and must not be committed to GitHub.
- SAS access is limited by the token's permissions and expiry.
- The container remains private; public access is not enabled.

## Outcome
Successfully configured and tested private Azure Blob Storage with temporary SAS-based file access and verified that unauthorized anonymous access was rejected.

## Technologies
Microsoft Azure | Azure Blob Storage | SAS | Cloud Security
