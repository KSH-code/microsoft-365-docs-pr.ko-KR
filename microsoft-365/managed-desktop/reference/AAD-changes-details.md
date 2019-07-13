---
title: Azure Active Directory 테 넌 트 세부 정보
description: 이 항목에서는 Microsoft Managed Desktop에서 등록할 때 AAD 계정의 변경 사항에 대해 설명 합니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643949"
---
# <a name="azure-active-directory-tenant-details"></a>Azure Active Directory 테 넌 트 세부 정보
{gory 계정, API calls, perms 등)에 대 한 세부 정보}


## <a name="data-transmitted-to-and-from-your-aad-account"></a>AAD 계정에 전송 되는 데이터


Microsoft의 계정으로 전송 되는 데이터:

- 그룹 이름
- 보안 정책 구성
- 장치 주문
- 사용자 계정 (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)
- E5 사용자 계정에 대 한 라이선스 할당
- 업데이트 링에 대 한 Windows update 정책

계정에서 Microsoft로 전송 되는 데이터:

- 장치 업데이트, 사용 현황 및 안정성 데이터
- 앱 배포 및 안정성 데이터
- 업데이트 및 보안 정책 배포 데이터
- 장치에 할당 된 사용자  

계정에서 전송 되는 데이터는 미국 내에서 호스트 되는 Microsoft 테 넌 트의 Azure SQL 데이터베이스에 저장 됩니다. 데이터는 {Microsoft Azure security}에 설명 된 정책에 따라 저장 및 처리 됩니다. 

## <a name="api-permissions-and-calls"></a>API 사용 권한 및 통화

**등록 중:**

API 사용 권한:
- DeviceManagementServiceConfig All
- Directory AccessAsUser. 모든
- 사용자. ReadWrite. 모두
- DeviceManagementConfiguration All
- DeviceManagementManagedDevices All
- 그룹. a i a. 모두

API 호출:
- 게시물/organization/{organizationId}/setMobileDeviceManagementAuthority
- GET/POST/directory역할/구성원 id
- GET/POST/users
- GET/POST/groups
- PATCH/p/p/{id}
- GET/POST/deviceManagement/deviceConfigurations
- /DeviceManagement/detectedApps 가져오기

**등록 후 일반적인 관리 작업을 수행 합니다.**

API 사용 권한:
- DeviceManagementManagedDevices All
- DeviceManagementApps All
- DeviceManagementConfiguration All
- 보고서. 모두
- 사용자. ReadWrite. 모두
- 그룹. a i a. 모두
- Directory AccessAsUser. 모든

API 호출:
- GET/POST/directory역할/구성원 id
- GET/PATCH/POST/users
- GET/POST/groups
- PATCH/p/p/{id}
- GET/POST/deviceManagement/deviceConfigurations
- GET/POST/deviceAppManagement/mobileApps
- /DeviceManagement/detectedApps 가져오기
- GET/devices
- 게시물/사용자/{id | userPrincipalName}/라이선스 할당
- /SubscribedSkus 가져오기

## <a name="accounts-used-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 사용 되는 계정





| Account | 설명  | 조건부 액세스  | Multi-Factor Authentication  | 정상 인 이유 |
|---------|---------|---------|---------|--------------|
| msadmin @ * onmmicrosoft .com | Microsoft Intune 및 사용자 관리자로 사용 되는 제한 된 서비스 계정 (관리자 권한) {what?} Microsoft 최신 데스크톱 장치에 대 한 테 넌 트를 정의 하 고 구성 합니다.대화형 로그인 권한이 없습니다. 서비스를 통해서만 작업을 수행 합니다.  | 네트워크에서 시작 되지 않으므로 제외 됩니다.        | 대화형 로그온이 없기 때문에 제외 됩니다.        | Azure 키 자격 증명 모음에 저장 된 암호 |
| mstest @ * onmmicrosoft .com     |         |         |         |
| mssupport @ * onmmicrosoft .com     |         |         |         |
| msadminint @ * onmmicrosoft .com     |         |         |         |
