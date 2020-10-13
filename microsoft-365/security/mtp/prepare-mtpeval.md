---
title: Microsoft Threat Protection 평가판 랩 환경 준비
description: Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 설정할 때 이해 관계자의 승인, 일정, 환경 고려 사항 및 채택 순서 준비
keywords: MTP 평가판 준비, MTP 파일럿 준비, MTP 파일럿 프로젝트 실행을 위한 준비, 파일럿 MTP 프로젝트, 배포, 준비, 관련자, 일정, 환경, 끝점, 서버, 관리, 도입
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 79e30ee6fd68148543a63377d89fe2955f276f24
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446734"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비" />
      <br/>1 단계: 준비 </a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 설정" />
      <br/>2 단계: 설치 </a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="각 Microsoft Threat Protection 기둥 구성 및 끝점 온보드" />
      <br/>3 단계: 온보드 & 구성</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

현재 준비 단계입니다.


준비는 성공적인 배포의 핵심입니다. 이 섹션에서는 Microsoft Threat Protection 배포를 위한 시험 운용 랩 또는 파일럿 환경을 만들기 위해 준비할 때 고려해 야 할 사항을 안내 합니다.

## <a name="prerequisites"></a>필수 구성 요소
Microsoft Threat Protection을 프로 비전 하 고 사용 하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다. Microsoft [Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [microsoft Defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [OFFICE 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)에 대 한 최소 요구 사항을 참조 하세요.

## <a name="stakeholders-and-sign-off"></a>관련자 및 승인
평가 또는 파일럿 프로젝트 실행에 관계 없이 프로젝트와 관련 된 모든 관련자와 승인, 검토 또는 계속 해 서 정보를 제공 해야 할 수 있습니다.

>[!NOTE]
>모든 조직이 보안 조직 성숙도를 보유 하 고 있는 것은 아닙니다. 이러한 경우 검토 및 승인 책임에 대 한 팀장 팀에 문의 하십시오.

조직에 적합 한 아래 표에 관련자를 추가 합니다.

-   SO =이 프로젝트에 대 한 승인

-   R =이 프로젝트를 검토 하 고 입력을 제공 합니다.

-   I =이 프로젝트에 대 한 정보

| 이름                 | 역할                                                                                                                                                                                                          | 작업 |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| 이름 및 전자 메일 입력 | **최고 정보 보안 담당자 (CISO)** *새 기술 배포를 위해 조직 내에서 스폰서 역할을 하는 임원 담당자입니다.*                                                  | 하면     |
| 이름 및 전자 메일 입력 | **사이버 (cdoc)의 머리** *이 변경 내용이 고객 보안 운영 팀의 프로세스와 부합 되는 방식을 정의 하는 방법을 담당 하는 cdoc 팀의 대표입니다.*       | 하면     |
| 이름 및 전자 메일 입력 | **보안 설계자** 는 *이 변경 내용이 조직의 핵심 보안 아키텍처에 부합 되는 방식을 정의 하는 방식으로 보안 팀의 담당자를 담당 합니다.*                         | 이력서      |
| 이름 및 전자 메일 입력 | **회사 설계자** 는 *IT 팀의 담당자가 조직의 핵심 작업 사이트 아키텍처와이 변경 사항을 맞추는 방법을 정의 하는 작업을 담당 합니다.*                             | 이력서      |
| 이름 및 전자 메일 입력 | **보안 분석가** 는 *보안 작업 측면에서의 검색 기능, 사용자 환경 및이 변경의 전반적인 유용성에 대 한 의견을 제공할 수 있는 cdoc 팀의 담당자입니다.* | 때      |

## <a name="prepare-your-azure-active-directory"></a>Azure Active Directory 준비
Active Directory와 Azure Active Directory 간의 동기화를 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다. Azure Active Directory에서 기존 모범 사례 설명서를 검토 합니다. 다음 단계는 파일럿 Microsoft Threat Protection 프로젝트를 평가 하거나 실행 하도록 최적화 되어 있습니다.

1. Azure **AD Connect**> [azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) 포털로 이동 합니다. 
![Azure Active Directory 포털 페이지 이미지](../../media/mtp-eval-1.png) <br> 

2. **Microsoft Azure Active Directory Connect** 에서 **다운로드** 를 클릭 하 고 도메인 컨트롤러로 전송 합니다.
![Azure 활성 Directoru 연결 다운로드 페이지 이미지](../../media/mtp-eval-2.png) <br>

3. 도메인 컨트롤러에서 Azure Active Directory 연결 마법사를 따릅니다. 사용권 조항 및 개인 정보 취급 방침을 읽고 동의할 경우 확인란을 선택 합니다. **계속**을 클릭합니다.
![Azure AD Connect 환영 페이지 이미지](../../media/mtp-eval-3.png) <br>

4. **빠른 설정**으로 이동 합니다.
![Express 설정 이미지 페이지](../../media/mtp-eval-4.png) <br>

5. 전역 관리자 자격 증명을 입력 합니다. **다음**을 클릭합니다.
![전역 관리자 자격 증명을 입력 해야 하는 Azure AD 연결 페이지의 이미지](../../media/mtp-eval-5.png) <br>

6. Active Directory 도메인 서비스 엔터프라이즈 관리자 자격 증명을 입력 합니다. **다음**을 클릭합니다.
![자격 증명을 입력 해야 하는 AD DS 페이지에 연결 되는 이미지](../../media/mtp-eval-6.png) <br>

7. **설치** 를 클릭 하 여 구성을 확인 합니다.
![구성 확인 페이지 이미지](../../media/mtp-eval-7.png) <br>

8. 축 하 합니다, Azure Active Directory Connect를 구성 했습니다.
![성공적으로 구성 된 Azure Active Directory Connect 페이지 이미지](../../media/mtp-eval-8.png) <br>

이제 [Active Directory에 사용자 및 그룹을 추가](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) 하 고 [SAM 정책을 구성할](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)수 있습니다.  


## <a name="configuration-order"></a>구성 순서
다음 표에는 Microsoft에서 평가 랩 또는 파일럿 환경 배포를 위한 Microsoft Threat Protection 구성 요소를 구성 하는 데 권장 되는 순서가 나와 있습니다.

| 구성 요소                               | 설명                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | 구성 순서 순위 |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Office 365 Advanced Threat Protection| Office 365 ATP는 전자 메일 메시지, 링크 (Url) 및 공동 작업 도구로 인해 야기 되는 악의적인 위협 으로부터 조직을 보호 합니다. <br> [더 알아보세요.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                    |
|Azure Advanced Threat Protection|Azure ATP는 Active Directory 신호를 사용 하 여 조직에서 진행 되는 고급 위협, 손상 된 id 및 악의적인 참가자 작업을 식별, 감지 및 조사 합니다. <br> [자세히 알아보기](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security는 여러 클라우드에서 작동 하는 "CASB (Cloud Access Security Broker)"입니다. 이를 통해 다양 한 가시성, 데이터 이동에 대 한 제어, 모든 클라우드 서비스에서 cyberthreats을 식별 하 고 공격 하는 정교한 분석이 제공 됩니다. <br> [자세히 알아보기](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                    |
|Microsoft Defender Advanced Threat Protection | Microsoft Defender ATP 엔드포인트 탐지 및 대응 기능은 실시간에 근접하고 조치가 가능한 고급 공격 탐지력을 제공합니다. 보안 분석가는 알림에 효과적으로 우선 순위를 지정하고, 침해의 전체 범위에 대한 가시성을 확보하고 위협을 수정하기 위한 대응 조치를 취할 수 있습니다. <br> [더 알아보세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>다음 단계
|![2 단계: 설치](../../media/setup.png) <br>[2 단계: 설치](setup-mtpeval.md) | Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 설정
|:-------|:-----|

