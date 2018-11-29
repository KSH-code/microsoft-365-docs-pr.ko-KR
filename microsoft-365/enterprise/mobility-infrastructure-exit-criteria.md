---
title: 모바일 장치 관리 인프라 종료 기준
description: Microsoft 365 Enterprise Microsoft Intune를 사용 하 여 모바일 장치 관리를 포함 합니다. 요구 사항 및 필수 구성 요소를 검토, Azure Active Directory 리소스를 사용 하 여 Intune 설정, iOS, macOS, Android, 및 Windows 등록 장치 앱을 배포, 구성 프로필 만들기, 규정 준수 정책 사용 및 모바일에 대 한 조건부 액세스를 사용 하도록 설정 Microsoft 365 엔터프라이즈와 장치 관리 합니다.
keywords: Microsoft 365, Microsoft 365 엔터프라이즈 모바일 장치 관리 Microsoft 365 Intune 설명서
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869890"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>모바일 장치 관리 인프라 종료 기준

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*이 Microsoft 365 Enterprise의 E3 및 e 5 버전에 적용 됩니다.*

배포 프로세스의 다음 단계로 이동 하기 전에 구성 모바일 장치 관리 인프라에 대 한 다음과 같은 요구 사항을 충족 하는지 확인 합니다.

- Intune이 설정되고 장치에 대한 조직 규칙을 적용할 Azure AD 사용자 및 그룹이 만들어집니다.
- 사용자가 만든 정책을 장치가 수락할 수 있도록 Intune에서 장치를 등록했습니다.
- 사용자가 Exchange Online 및 SharePoint Online과 같은 조직의 Microsoft 365 클라우드 서비스에 액세스할 수 있도록 장치에 앱이 추가됩니다.
- 사용자가 만든 Azure AD 사용자 및 그룹을 사용하여 바이러스 백신 사용 및 특정 앱 제한과 같은 기능이 구성되고 사용자 장치에 적용됩니다.
- 장치의 방화벽 또는 암호 길이를 요구하는 준수 정책이 설정됩니다. 장치가 규정을 준수하지 못하면 조건부 액세스 권한이 조직 데이터에 대한 액세스를 차단합니다.

## <a name="next-phase"></a>다음 단계

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Microsoft 365 enterprise-종단간 배포 프로세스의 다음 단계로 사용자 [정보 보호](infoprotect-infrastructure.md)하는 기능이 있습니다. |
