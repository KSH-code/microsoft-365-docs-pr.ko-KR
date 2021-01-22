---
title: Microsoft 365 Defender 평가판 랩 환경 준비
description: Microsoft 365 Defender 평가판 또는 파일럿 환경을 설정할 때 이해 관계자 서명, 타임라인, 환경 고려 사항 및 채택 순서를 준비합니다.
keywords: MTP 시험 준비, MTP 파일럿 준비, MTP 파일럿 프로젝트 실행 준비, 파일럿 MTP 프로젝트 실행, 배포, 준비, 이해 관계자, 타임라인, 환경, 끝점, 서버, 관리, 채택
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 35f1d3f0b5cefb0f14508571511449fc2c7d58a9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930153"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 준비

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 만들고 배포하는 과정은 3단계 프로세스입니다.

|![1단계: 준비](../../media/phase-diagrams/prepare.png)<br/>1단계: 준비 |[![2단계: 설정](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[2단계: 설정](setup-mtpeval.md) |[![3단계: 온보드](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[3단계: 온보드](config-mtpeval.md) | [![파일럿으로 돌아가기](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[파일럿 플레이북으로 돌아가기](mtp-pilot.md) |
|--|--|--|--|
|*You are here!* | || |

현재 준비 단계에 있습니다.


성공적인 배포의 핵심은 준비입니다. 이 섹션에서는 Microsoft 365 Defender 배포를 위한 시험 랩 또는 파일럿 환경을 만들기 위해 준비할 때 고려해야 할 부분을 안내합니다.

## <a name="prerequisites"></a>필수 구성 요소
Microsoft 365 Defender를 프로비전하고 사용하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 자세히 알아보습니다. [Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites) [끝점용 Microsoft Defender,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)Office [365용 Microsoft Defender,](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) [ID용 Microsoft Defender,](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)Microsoft Cloud App Security에 대한 최소 요구 사항을 [참조하세요.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)

## <a name="stakeholders-and-sign-off"></a>이해 관계자 및 사인오프
평가 또는 파일럿 프로젝트 실행 여부에 관계자 및 서명, 검토 또는 정보를 파악해야 할 수 있는 모든 관련자를 식별합니다.

>[!NOTE]
>일부 조직에는 보안 조직이 이러한 역할을 가지는 것이 성숙하지 않을 수 있습니다. 이 경우 리더십 팀에 검토 및 승인 책임에 대해 문의하세요.

조직에 따라 아래 표에 관련자를 추가합니다.

-   SO = 이 프로젝트에서 서명

-   R = 이 프로젝트 검토 및 입력 제공

-   I = 이 프로젝트에 대한 정보

| 이름                 | 역할                                                                                                                                                                                                          | 작업 |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 이름 및 전자 메일 입력 | **CISO(최고 정보 보안 책임자)는** 새 기술 배포를 위해 조직 내부의 스폰서 역할을 하는 *임원진 대표입니다.*                                                  | SO     |
| 이름 및 전자 메일 입력 | **CDOC(사이버** 방어 운영 센터) 담당자는 고객 보안 운영 팀의 프로세스와 이 변경이 어떻게 일치하는지 정의하는 담당 CDOC 팀의 *담당자입니다.*       | SO     |
| 이름 및 전자 메일 입력 | **이 변경이** 조직의 핵심 보안 아키텍처에 맞춰진 방식 정의를 담당하는 보안 팀의 보안 설계자 *A 담당자입니다.*                         | R      |
| 이름 및 전자 메일 입력 | **이 변경이** 조직의 핵심 작업 공간 아키텍처에 어떻게 부합하는지 정의하는 업무를 담당하는 IT 팀의 작업 공간 설계자 *A 담당자입니다.*                             | R      |
| 이름 및 전자 메일 입력 | **보안 분석가** A는 보안 운영 측면에서 이러한 변경의 감지 기능, 사용자 환경 및 전반적인 유용성에 대한 피드백을 제공할 수 있는 CDOC 팀의 *담당자입니다.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Azure Active Directory 준비
Active Directory와 Azure Active Directory 간의 동기화를 이미 사용하도록 설정한 경우 이 단계를 건너뜁합니다. Azure Active Directory의 기존 모범 사례 설명서를 검토합니다. 다음 단계는 파일럿 Microsoft 365 Defender 프로젝트를 평가하거나 실행하도록 최적화되어 있습니다.

1. [Azure AD Connect의 Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **이동하세요.** 
![Azure Active Directory 포털 페이지의 이미지](../../media/mtp-eval-1.png) <br> 

2. Microsoft  **Azure Active Directory Connect에서** 다운로드를 클릭하고 도메인 컨트롤러로 전송합니다.
![Azure Active Directoru Connect 다운로드 페이지의 이미지](../../media/mtp-eval-2.png) <br>

3. 도메인 컨트롤러에서 Azure Active Directory Connect 마법사를 따르십시오. 사용 조건 및 개인 정보 취급 방침을 읽고 동의하는 경우 확인란을 선택합니다. **계속** 을 클릭합니다.
![Azure AD Connect 시작 페이지의 이미지](../../media/mtp-eval-3.png) <br>

4. Express **설정으로 이동합니다.**
![Express 설정 페이지 이미지](../../media/mtp-eval-4.png) <br>

5. 전역 관리자 자격 증명을 입력합니다. **다음** 을 클릭합니다.
![전역 관리자 자격 증명을 입력해야 하는 Azure AD 페이지에 연결 이미지](../../media/mtp-eval-5.png) <br>

6. Active Directory 도메인 서비스 엔터프라이즈 관리자 자격 증명을 입력합니다. **다음** 을 클릭합니다.
![자격 증명을 입력해야 하는 AD DS에 연결 페이지 이미지](../../media/mtp-eval-6.png) <br>

7. **설치를** 클릭하여 구성을 확인할 수 있습니다.
![구성 확인 페이지 이미지](../../media/mtp-eval-7.png) <br>

8. 축하합니다. Azure Active Directory Connect를 성공적으로 구성했습니다.
![성공적으로 구성된 Azure Active Directory Connect 페이지의 이미지](../../media/mtp-eval-8.png) <br>

이제 Active [Directory에 사용자 및](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) 그룹을 추가하고 [SAM-R 정책을 구성할 수 있습니다.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>구성 순서
다음 표에는 평가판 또는 파일럿 환경 배포를 위해 Microsoft가 Microsoft 365 Defender 구성 요소를 구성하기 위해 권장하는 순서가 표시됩니다.

| 구성 요소                               | 설명                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 구성 순서 순위 |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Office 365용 Microsoft Defender|Office 365용 Microsoft Defender는 전자 메일 메시지, 링크 (URL) 및 공동 작업 도구로 인한 악의적인 위협으로부터 조직을 보호합니다. <br> [더 알아보세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                    |
|ID용 Microsoft Defender|Microsoft Defender for Identity는 Active Directory 신호를 사용하여 고급 위협, 손상된 ID 및 조직에 대한 악의적인 내부자 작업을 식별, 감지 및 조사합니다. <br> [자세한 정보](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security는 여러 클라우드에서 작동하는 CASB(클라우드 액세스 보안 브로커)입니다. 풍부한 가시성, 데이터 이동 제어 및 정교한 분석을 통해 모든 클라우드 서비스에서 사이버 위협을 식별하고 퇴치할 수 있습니다. <br> [자세한 정보](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|엔드포인트용 Microsoft Defender | 끝점 끝점 검색 및 응답 기능을 위한 Microsoft Defender는 거의 실시간으로 실행 가능한 고급 공격 감지를 제공합니다. 보안 분석가는 알림에 효과적으로 우선 순위를 지정하고, 침해의 전체 범위에 대한 가시성을 확보하고 위협을 수정하기 위한 대응 조치를 취할 수 있습니다. <br> [더 알아보세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>다음 단계
|![2단계: 설정](../../media/setup.png) <br>[2단계: 설정](setup-mtpeval.md) | Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 설정
|:-------|:-----|

