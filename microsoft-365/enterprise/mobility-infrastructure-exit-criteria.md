---
title: 모바일 장치 관리 인프라 종료 조건
description: microsoft 365 Enterprise는 microsoft Intune을 사용 하는 모바일 장치 관리를 포함 합니다. 요구 사항 및 필수 구성 요소를 검토 하 고, Azure Active Directory 리소스를 사용 하 여 Intune을 설정 하 고, iOS, macos, Android 및 Windows 장치를 등록 하 고, 앱을 배포 하 고, 프로필 구성, 준수 정책을 사용 하 고, 모바일에 조건부 액세스 사용 Microsoft 365 Enterprise를 사용한 장치 관리
keywords: microsoft 365, microsoft 365 Enterprise, microsoft 365 설명서, 모바일 장치 관리, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 14f216fe352d9108fe69028731f4c94dfb9d19f7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291235"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>모바일 장치 관리 인프라 종료 조건

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*이는 Microsoft 365 Enterprise E3 및 E5 버전에 적용 됩니다.*

구성이 모바일 장치 관리 인프라에 대 한 다음 요구 사항을 충족 하는지 확인 합니다.

- Intune이 설정되고 장치에 대한 조직 규칙을 적용할 Azure AD 사용자 및 그룹이 만들어집니다.
- 사용자가 만든 정책을 장치가 수락할 수 있도록 Intune에서 장치를 등록했습니다.
- 사용자가 Exchange Online 및 SharePoint Online과 같은 조직의 Microsoft 365 클라우드 서비스에 액세스할 수 있도록 장치에 앱이 추가됩니다.
- 사용자가 만든 Azure AD 사용자 및 그룹을 사용하여 바이러스 백신 사용 및 특정 앱 제한과 같은 기능이 구성되고 사용자 장치에 적용됩니다.
- 장치의 방화벽 또는 암호 길이를 요구하는 준수 정책이 설정됩니다. 장치가 규정을 준수하지 못하면 조건부 액세스 권한이 조직 데이터에 대한 액세스를 차단합니다.



## <a name="results-and-next-steps"></a>결과 및 다음 단계

장치가 Intune에 등록 되 고 적절 한 정책으로 구성 됩니다.

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Microsoft 365 Enterprise의 종단 간 배포를 위한 단계를 수행 하는 경우 다음 단계는 [정보 보호](infoprotect-infrastructure.md)입니다. |
