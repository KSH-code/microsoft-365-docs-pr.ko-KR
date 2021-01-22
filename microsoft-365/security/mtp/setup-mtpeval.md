---
title: Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 설정
description: Microsoft 365 보안 센터에 액세스한 다음 Microsoft 365 Defender 평가판 랩 환경 설정
keywords: Microsoft Threat Protection 평가판 설정, Microsoft Threat Protection 파일럿 설정, Microsoft Threat Protection 체험, Microsoft Threat Protection 평가 랩 설정
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
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932985"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Microsoft 365 Defender 평가판 랩 환경 설정 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender 


Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 만들고 배포하는 과정은 3단계 프로세스입니다.

|[![1단계: 준비](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[1단계: 준비](prepare-mtpeval.md) |![2단계: 설정](../../media/phase-diagrams/setup.png)<br/>2단계: 설정 |[![3단계: 온보드](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[3단계: 온보드](config-mtpeval.md) | [![파일럿으로 돌아가기](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[파일럿 플레이북으로 돌아가기](mtp-pilot.md) |
|--|--|--|--|
||*You are here!*  | | |


현재 설정 단계에 있습니다. 초기 단계를 수행하여 Microsoft 365 보안 센터에 액세스한 다음 시험 랩 또는 파일럿 환경을 설정하세요.

Office 365 또는 Azure Active Directory 구독에 등록하여 Microsoft 365 E5 *라이선스에 등록하는 데 사용할 수 있는 .onmicrosoft.com* 테넌트 생성 

>[!NOTE]
>기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우 Office 365 E5 평가판 또는 파일럿 테넌트 만들기 단계를 건너뛸 수 있습니다.

이 단계에서는 다음을 안내합니다.
- Office 365 E5 평가판 테넌트 만들기
- Microsoft 365 평가판 구독 사용


## <a name="create-an-office-365-e5-trial-tenant"></a>Office 365 E5 평가판 테넌트 만들기
>[!NOTE]
>기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우 Office 365 E5 평가판 테넌트 만들기 단계를 건너뛸 수 있습니다.

1. [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 제품 포털로 이동하고 무료 **평가판을 선택합니다.**

   ![이미지 of_Office 365 E5 무료 평가판 페이지](../../media/mtp-eval-9.png)
  
2. 전자 메일 주소(개인 또는 회사)를 입력하여 평가판 등록을 완료합니다. 계정 **설정을 클릭합니다.**

   ![이미지 of_Office 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-10.png)

3. 이름, 성, 회사 전화 번호, 회사 이름, 회사 규모, 국가 또는 지역을 입력합니다.  

   ![이름of_Office 전화 및 회사 세부 정보를 묻는 이미지 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > 여기서 설정한 국가 또는 지역은 Office 365가 호스팅되는 데이터 센터 지역을 결정합니다.
  
4. 확인 기본 설정(문자 메시지 또는 전화를 통해)을 선택하십시오. 확인 **코드 보내기 를 클릭합니다.** 

   ![확인 of_Office 묻는 이미지 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-12.png)

5. 테넌트의 사용자 지정 도메인 이름을 설정하고 다음을 **클릭합니다.**

   ![사용자 지정 of_Office 설정할 수 있는 이미지 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-13.png)
 
6. 테넌트에 대한 전역 관리자가 될 첫 번째 ID를 설정합니다. 이름과 **암호를** **입력합니다.** **로그인** 을 클릭합니다.

   ![비즈니스 of_Office 설정할 수 있는 이미지 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-14.png)

7. 설치로 **이동을 클릭하여** Office 365 E5 평가판 테넌트 프로비전을 완료합니다.

   ![설치 이동 단추를 클릭하라는 Office 365 E5 평가판 등록 설정 페이지의 이미지](../../media/mtp-eval-15.png)

8. 회사 도메인을 Office 365 테넌트에 연결합니다. [선택 사항] Choose **Connect a domain you already own** and type in your domain name. **다음** 을 클릭합니다.

   ![로그인 of_Office 전자 메일을 개인 설정해야 하는 365 E5 설치 페이지 이미지](../../media/mtp-eval-16.png)
 
9. 도메인 소유권의 유효성을 검사하려면 TXT 또는 MX 레코드를 추가합니다. 도메인에 TXT 또는 MX 레코드를 추가한 후 확인을 **선택합니다.**

   ![도메인을 확인하기 위해 MX 레코드의 TXT를 추가해야 하는 이미지 of_Office 365 E5 설치 페이지](../../media/mtp-eval-17.png)
 
10. [선택 사항] 테넌트에 대한 사용자 계정을 더 만들 수 있습니다. 다음을 클릭하여 이 단계를 건너뛸 **수 있습니다.**

    ![더 많은 of_Office 수 있는 이미지 365 E5 설치 페이지](../../media/mtp-eval-18.png)
 
11. [선택 사항] Office 앱을 다운로드합니다. 다음을 **클릭하여** 이 단계를 건너뜁습니다. 

    ![Office of_Office 설치할 수 있는 이미지 365 E5 페이지](../../media/mtp-eval-19.png)

12. [선택 사항] 전자 메일 메시지를 마이그레이션합니다. 이 단계를 건너뛸 수 있습니다.

    ![전자 메일 of_Office 마이그레이션할지 여부를 설정할 수 있는 이미지 365 E5](../../media/mtp-eval-20.png)
 
13. 온라인 서비스를 선택하세요. Exchange를 **선택하고** 다음을 **클릭합니다.** 

    ![온라인 of_Office 선택할 수 있는 이미지 365 E5](../../media/mtp-eval-21.png)

14. 도메인에 MX, CNAME 및 TXT 레코드를 추가합니다. 완료되면 확인을 **선택합니다.**

    ![여기에서 of_Office 365 E5를 사용하여 DNS 레코드를 추가할 수 있습니다.](../../media/mtp-eval-22.png)
 
15. 축하합니다. Office 365 테넌트의 프로비전을 완료했습니다.

    ![이미지 of_Office 365 E5 설치 완료 확인 페이지](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365 평가판 구독 사용

>[!NOTE]
>평가판에 등록하면 한 달 동안 사용할 25개 사용자 라이선스가 부여됩니다. 자세한 [내용은 M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 구독 시도 또는 구입을 참조하세요.

1. [Microsoft 365 관리 센터에서](https://admin.microsoft.com/)청구를 클릭한 다음 서비스 **구매로 이동합니다.** 

2. **Microsoft 365 E5를 선택하고** **평가판 시작을 클릭합니다.** 

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지](../../media/mtp-eval-24.png)

3. 확인 기본 설정(문자 메시지 또는 전화를 통해)을 선택하십시오. 결정한 후 전화 번호를 입력하고  선택에  따라 문자 메시지 또는 전화 걸기를 선택합니다.

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 로봇이 아 아니라는 것을 증명하기 위해 코드를 보내기 위한 연락처 세부 정보를 요청하는 무료 평가판 페이지](../../media/mtp-eval-25.png)
 
4. 인증 코드를 입력하고 무료 **평가판 시작을 클릭합니다.**

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 시스템이 로봇이 아 아니라는 것을 증명하기 위해 전송된 검증 코드를 입력할 수 있습니다.](../../media/mtp-eval-26.png)

5. 지금 **사용해 보시고** Microsoft 365 E5 평가판을 확인하세요.

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 지금 체험 단추를 시작해야 합니다.](../../media/mtp-eval-27.png)
 
6. **Microsoft 365 관리** 센터 사용자 활성  >    >  **사용자로 이동하세요.** 사용자 계정을 선택하고 제품 라이선스 관리를 선택한 다음 Office 365 E5에서 **Microsoft 365 E5로** 라이선스를 교체합니다. **저장** 을 클릭합니다.

   ![Microsoft of_Microsoft 365 E5 라이선스를 선택할 수 있는 365 관리 센터 페이지 이미지](../../media/mtp-eval-28.png)
 
7. 전역 관리자 계정을 다시 선택한 다음 사용자 이름 **관리를 클릭합니다.**

   ![이미지를 of_Microsoft 365 관리 센터 페이지에서 계정을 선택한 다음 사용자 이름을 관리할 수 있습니다.](../../media/mtp-eval-29.png)

8. [선택 사항] 이전 단계에서  onmicrosoft.com 따라 도메인을 사용자 도메인으로 변경합니다. **변경 사항 저장** 를 클릭합니다.

   ![도메인 of_Microsoft 변경할 수 있는 365 관리 센터 페이지 이미지](../../media/mtp-eval-30.png)



## <a name="next-step"></a>다음 단계
|[3단계: 온보드 & 구성](config-mtpeval.md) | Microsoft 365 Defender 평가판 랩 또는 파일럿 환경에 대해 각 Microsoft 365 Defender 기조를 구성하고 끝점을 온보딩합니다.
|:-------|:-----|
