---
title: Microsoft Threat Protection 평가판 랩 환경 설정
description: Microsoft 365 보안 센터에 액세스 한 후 Microsoft Threat Protection 평가판 랩 환경 설정
keywords: Microsoft Threat Protection 평가판 설치, microsoft threat protection, Microsoft Threat Protection 평가 실험 설정 시도
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 69a883263952b7c20225659ae023399e0242606d
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650072"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Microsoft Threat Protection 평가판 랩 환경 설정 

**적용 대상:**
- Microsoft 위협 방지 


Microsoft Threat Protection 평가판 랩 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가 랩 준비" />
      <br/>1 단계: 준비 </a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가 랩 설정" />
      <br/>2 단계: 설치 </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Microsoft Threat Protection 평가판 테스트 환경에 대 한 각 Microsoft Threat Protection을 구성 하 고 끝점을 온보드" />
      <br/>3 단계: 온보드 & 구성 </a><br>
</td>


  </tr>
</table>

현재 설정 단계입니다. 초기 단계를 수행 하 여 Microsoft 365 보안 센터에 액세스 한 다음 평가판 랩 환경을 설정 합니다.

Microsoft 365 E5 라이선스를 등록 하는 데 사용할 수 있는 *onmicrosoft.com* 테 넌 트를 생성 하기 위해 Office 365 또는 Azure Active Directory 구독에 등록 합니다. 

>[!NOTE]
>기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우에는 Office 365 E5 평가판 테 넌 트 만들기 단계를 건너뛸 수 있습니다.

이 단계에서는 다음을 안내 합니다.
- Office 365 E5 평가판 테 넌 트 만들기
- Microsoft 365 평가판 구독 사용


## <a name="create-an-office-365-e5-trial-tenant"></a>Office 365 E5 평가판 테 넌 트 만들기
>[!NOTE]
>기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우에는 Office 365 E5 평가판 테 넌 트 만들기 단계를 건너뛸 수 있습니다.

1. [Office 365 E5 제품 포털로](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 이동 하 여 **무료 평가판**을 선택 합니다.
![이미지 of_Office 365 E5 무료 평가판 페이지](../../media/mtp-eval-9.png) <br>
  
2. 전자 메일 주소 (개인 또는 회사)를 입력 하 여 평가판 등록을 완료 합니다. **계정 설정을**클릭 합니다.
![이미지 of_Office 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-10.png) <br> 

3. 성, 성, 근무처 전화 번호, 회사 이름, 회사 크기, 국가 또는 지역을 입력 합니다.  
<br>![이미지 of_Office 365 E5 평가판 등록 설정 페이지 이름, 전화 번호 및 회사 정보를 요청 합니다.](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>여기에서 설정 하는 국가 또는 지역에 따라 Office 365이 호스팅될 데이터 센터 지역이 결정 됩니다.
  
4. 텍스트 메시지 또는 통화를 통해 확인 기본 설정을 선택 합니다. **확인 코드 보내기를**클릭 합니다. 
![이미지 of_Office 365 E5 평가판 등록 설정 페이지 확인 기본 설정 요청](../../media/mtp-eval-12.png) <br>

5. 테 넌 트에 대 한 사용자 지정 도메인 이름을 설정 하 고 **다음**을 클릭 합니다.
<br>![Image of_Office 365 E5 평가판 등록 설정 페이지에서 사용자 지정 도메인 이름을 설정할 수 있습니다.](../../media/mtp-eval-13.png) <br>
 
6. 테 넌 트에 대 한 전역 관리자가 될 첫 번째 id를 설정 합니다. **이름** 및 **암호**를 입력 합니다. **로그인**을 클릭합니다.
![이미지 of_Office 365 E5 평가판 등록 설정 페이지에서 비즈니스 id를 설정할 수 있습니다.](../../media/mtp-eval-14.png) <br>

7. Office 365 E5 평가판 테 넌 트 프로 비전을 완료 하려면 **설치로 이동을** 클릭 합니다.
<br>![Office 365 E5 평가판 등록 설정 페이지에서 이동 설정 단추를 클릭 하 라는 메시지가 표시 되는 모양](../../media/mtp-eval-15.png) <br>

8. 회사 도메인을 Office 365 테 넌 트에 연결 합니다. 반드시 **이미 소유한 도메인 연결** 을 선택 하 고 도메인 이름을 입력 합니다. **다음**을 클릭합니다.
<br>![사용자의 로그인 및 전자 메일을 개인 설정 해야 하는 이미지 of_Office 365 E5 설정 페이지](../../media/mtp-eval-16.png) <br>
 
9. 도메인 소유권을 확인 하려면 TXT 또는 MX 레코드를 추가 해야 합니다. TXT 또는 MX 레코드를 도메인에 추가한 후에는 **확인**을 선택 합니다.
<br>![이미지 of_Office 365 E5 설치 페이지 도메인을 확인 하려면 MX 레코드의 TXT를 추가 해야 합니다.](../../media/mtp-eval-17.png) <br>
 
10. 반드시 테 넌 트에 대 한 사용자 계정을 더 만듭니다. **다음**을 클릭 하 여이 단계를 건너뛸 수 있습니다.
![이미지 of_Office 365 E5 설치 페이지 더 많은 사용자를 추가할 수 있습니다.](../../media/mtp-eval-18.png) <br>
 
11. 반드시 Office 앱을 다운로드 합니다. 이 단계를 건너뛰려면 **다음** 을 클릭 합니다. 
<br>![Office 앱을 설치할 수 있는 이미지 of_Office 365 E5 페이지](../../media/mtp-eval-19.png) <br>

12. 반드시 전자 메일 메시지를 마이그레이션합니다. 이 단계를 건너뛸 수 있습니다.
<br>![이미지 of_Office 365 E5 전자 메일 메시지를 마이그레이션할지 여부를 설정할 수 있습니다.](../../media/mtp-eval-20.png) <br>
 
13. 온라인 서비스를 선택 합니다. **Exchange** 를 선택 하 고 **다음**을 클릭 합니다. 
<br>![온라인 서비스를 선택할 수 있는 365 E5 이미지 of_Office](../../media/mtp-eval-21.png) <br>

14. 도메인에 MX, CNAME 및 TXT 레코드를 추가 합니다. 완료 되 면 **확인**을 선택 합니다.
<br>![Image of_Office 365 E5 여기에서 DNS 레코드를 추가할 수 있습니다.](../../media/mtp-eval-22.png) <br>
 
15. 축 하 합니다, Office 365 테 넌 트의 프로 비전을 완료 했습니다.
<br>![이미지 of_Office 365 E5 설치 완료 확인 페이지](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365 평가판 구독 사용

>[!NOTE]
>평가판에 등록 하면 월별 사용자 라이선스 25 개를 사용할 수 있습니다. 자세한 내용은 [M365 구독을 시도해 보거나 구매](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) 를 참조 하세요.

1. [Microsoft 365 관리 센터](https://admin.microsoft.com/)에서 **대금 청구** 를 클릭 하 고 **서비스 구매**로 이동 합니다.

2. **Microsoft 365 E5** 를 선택 하 고 **무료 평가판 시작**을 클릭 합니다. 
![Image of_Microsoft 365 E5 Start 무료 평가판 페이지](../../media/mtp-eval-24.png) <br>

3. 텍스트 메시지 또는 통화를 통해 확인 기본 설정을 선택 합니다. 전화 번호를 입력 하 고 **선택한 내용에** 따라 통화를 선택 하거나 **내게 전화** 를 해야 합니다.
![이미지 of_Microsoft 365 E5 시작 무료 평가판 페이지에서 로봇을 증명할 코드를 보내도록 연락처 정보를 요청 합니다.](../../media/mtp-eval-25.png) <br>
 
4. 확인 코드를 입력 하 고 **무료 평가판 시작**을 클릭 합니다. 
<br>![Image of_Microsoft 365 E5 Start 무료 평가판 페이지에서 사용자가 로봇이 아님을 입증 하기 위해 전송 되는 시스템의 확인 코드를 작성할 수 있습니다.](../../media/mtp-eval-26.png) <br>

5. Microsoft 365 E5 평가판을 확인 하려면 **지금 시도** 를 클릭 합니다.
<br>![Image of_Microsoft 365 E5 Start 무료 평가판 페이지를 시작 하려면 지금 사용해 보기 단추를 클릭 합니다.](../../media/mtp-eval-27.png) <br>
 
6. **Microsoft 365 관리 센터**  >  **사용자**  >  **활성 사용자**로 이동 합니다. 사용자 계정을 선택 하 고 **제품 라이선스 관리**를 선택한 다음 Office 365 E5에서 **Microsoft 365 e5**로 라이선스를 바꿉니다. **저장**을 클릭합니다.
![Image of_Microsoft 365 관리 센터 페이지 Microsoft 365 E5 라이선스를 선택할 수 있습니다.](../../media/mtp-eval-28.png) <br>
 
7. 전역 관리자 계정을 다시 선택 하 고 **사용자 이름 관리**를 클릭 합니다.
<br>![이미지 of_Microsoft 365 관리 센터 페이지 계정을 선택 하 고 사용자 이름을 관리할 수 있습니다.](../../media/mtp-eval-29.png) <br>

8. 반드시 이전 단계에서 선택한 사항에 따라 도메인을 *onmicrosoft.com* 에서 자체 도메인으로 변경 합니다. **변경 내용 저장**을 클릭합니다.
<br>![이미지 of_Microsoft 365 관리 센터 페이지 도메인 기본 설정을 변경할 수 있음](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>다음 단계
![3 단계: 온보드 & 구성](../../media/config-onboard.png) <br>[3 단계: 온보드 & 구성](config-mtpeval.md) <br>Microsoft Threat Protection 평가 랩에서 각 Microsoft Threat Protection을 구성 하 고 끝점을 등록 합니다.
