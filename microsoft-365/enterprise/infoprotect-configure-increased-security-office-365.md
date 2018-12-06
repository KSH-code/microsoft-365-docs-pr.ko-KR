---
title: '3단계: Office 365에 대한 향상된 보안 구성'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Office 365 ATP를 포함하여 Office 365에 대한 향상된 보안을 이해하고 구성합니다.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870245"
---
# <a name="step-3-configure-increased-security-for-office-365"></a>3단계: Office 365에 대한 향상된 보안 구성

*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Office 365 구독과 해당 데이터가 시작되고 악의적인 위협으로부터 안전하게 유지되는지 확인하려면 [향상된 보안을 위한 Office 365 테넌트 구성](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)을 참조하여 다음 추가 보안을 구성하세요.

- Office 365 보안 및 준수 센터의 위협 관리 정책
- 추가 Exchange Online 테넌트 수준 설정
- SharePoint 관리 센터의 테넌트 수준 공유 정책
- Azure Active Directory의 설정

구성한 후에는 다음에서 보안 상태에 대한 정보를 얻을 수 있습니다.

- 보안 및 준수 센터의 대시보드 및 보고서
- [Office 365 보안 점수](https://securescore.office.com/)
 
  이 페이지에 액세스하려면 Office 365 테넌트 관리자로 로그인해야 합니다.

Cloud App Security 또는 Office 365 Cloud App Security를 사용하여 보안 이벤트 및 작업을 모니터링할 수도 있습니다. 자세한 내용은 [Office 365 Cloud App Security 개요](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475)를 참조하세요.

추가 보안 기능은 조직에서 다음을 통해 보다 안전하게 공동 작업하는 데 도움이 되는 Office 365 ATP(Advanced Threat Protection)입니다.

- 전자 메일의 링크 및 첨부 파일 보호 
- Exchange Online의 전자 메일과 SharePoint Online, 비즈니스용 OneDrive 및 Microsoft Teams의 OneDrive 파일에 대해 스푸핑 인텔리전스 및 피싱 방지 기능 제공 

>[!Note]
>Office 365 ATP는 Microsoft 365 Enterprise E5에 포함되어 있습니다. Microsoft 365 Enterprise E3이 있는 경우 ATP에 대한 개별 라이선스를 구입할 수 있습니다.
>

Office 365 ATP를 사용하려면 [설정](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)을 참조하세요.

자세한 내용은 [SharePoint, OneDrive 및 Microsoft Teams에 대한 Office 365 ATP](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607)를 참조하세요.


|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 강화된 Office 365 보안 구성](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

중간 검사점으로 이 단계에 해당하는 [종료 조건](infoprotect-exit-criteria.md#crit-infoprotect-step4)을 확인하세요.

## <a name="next-step"></a>다음 단계


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[권한이 부여된 액세스 관리 구성](infoprotect-configure-privileged-access-management.md)|


