---
title: Windows 10 PC에서 장치 보호 설정 설정하기
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: 기본 및 Windows 10 장치 보호 하기 위해 Microsoft 365 비즈니스에서 사용할 수 있는 기타 설정 하는 방법에 대 한 설명 합니다.
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869715"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a>Windows 10 PC에서 장치 보호 설정 설정하기

## <a name="secure-windows-10-devices"></a>Windows 10 장치 보안

Microsoft 365 Business를 사용하여 Windows 10 장치를 안전하게 보호하는 방법에 대한 비디오를 시청하세요.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. 전역 관리자 자격 증명을 사용하여 [Microsoft 365 Business](https://portal.office.com)에 로그인합니다. 
    
2. 관리 센터의 **장치 정책** 카드에서 **정책 추가**를 선택합니다.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. **정책 추가** 창에서 이 정책의 고유 이름을 입력합니다. 
    
4. **정책 유형**에서 **Windows 10 장치 구성**을 선택합니다.
    
5. 확장 **Windows 10 장치 보안을 유지** 하 고 \> 하려는 방식 설정을 구성 합니다. 자세한 내용은 [사용할 수 있는 설정](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) 을 참조 하십시오. 
    
    언제든지 **기본 설정 다시 설정** 링크를 사용하여 기본 설정으로 돌아갈 수 있습니다. 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. 다음 결정 **가 이러한 설정을 받아볼?** 이러한 설정은 받아볼 수 있는 보안 그룹에 대 한 기본 **모든 사용자에 게** 보안 그룹 선택 **변경**를 사용 하 여 않으려면 검색 \> **을 선택**합니다.
    
7. 마지막으로 **완료**를 선택하여 정책을 저장하고 장치를 할당합니다. 
    
## <a name="available-settings"></a>사용 가능한 설정

모든 설정의 기본값은 **켬**입니다. 다음과 같은 설정을 사용할 수 있습니다.
  
자세한 내용은 [Microsoft 365 Business의 보호 기능을 Intune 설정에 매핑하는 방법](map-protection-features-to-intune-settings.md)을 참조하세요. 
  
|||
|:-----|:-----|
|설정  <br/> |설명  <br/> |
|Windows Defender Antivirus를 사용하여 바이러스 및 기타 위협으로부터 PC를 보호하도록 지원  <br/> |인터넷에 연결하여 발생할 수 있는 위험으로부터 PC를 보호하기 위해 Windows Defender Antivirus가 켜져 있어야 합니다.  <br/> |
|Microsoft Edge에서 웹 기반 위협으로부터 PC를 보호하도록 지원  <br/> |Edge에서 사용자를 악성 사이트와 다운로드로부터 보호하는 설정을 켭니다.  <br/> |
|장치의 공격 표면을 줄이는 규칙 사용  <br/> |'켬'으로 설정하면 공격 표면이 감소하여 일반적으로 맬웨어가 장치를 감염시키는 데 사용되는 작업 및 앱을 차단할 수 있습니다. 이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다. 자세한 내용은 [공격 표면 축소](https://go.microsoft.com/fwlink/?linkid=870417)를 참조하세요.  <br/> |
|랜섬웨어와 같은 위협으로부터 폴더 보호  <br/> |이 설정은 제어된 폴더 액세스를 사용하여 랜섬웨어와 같은 의심스러운 앱이나 악성 앱에 의해 회사 데이터가 수정되는 것을 방지합니다. 이러한 유형의 앱은 보호된 폴더를 변경할 수 없도록 차단됩니다. 이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다. 자세한 내용은 [제어된 폴더 액세스를 사용하여 폴더 보호](https://go.microsoft.com/fwlink/?linkid=870418)를 참조하세요.  <br/> |
|인터넷의 의심스러운 콘텐츠에 대한 네트워크 액세스 차단  <br/> |피싱 메일, 익스플로잇 또는 기타 악의적 콘텐츠를 호스트할 수 있는 평판이 낮은 인터넷 위치에 대한 아웃바운드 사용자 연결을 차단하려면 이 설정을 사용합니다. 이 설정은 Windows Defender 바이러스 백신을 '켬'으로 설정한 경우에만 사용할 수 있습니다. 자세한 내용은 [네트워크 보호](https://go.microsoft.com/fwlink/?linkid=870419)를 참조하세요.  <br/> |
|BitLocker를 사용하여 PC의 파일 및 폴더를 무단 액세스로부터 보호  <br/> |Bitlocker는 컴퓨터 하드 드라이브를 암호화하여 데이터를 보호하고, 컴퓨터가 분실되거나 도난당한 경우 데이터 노출을 방지합니다. 자세한 내용은 [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000)를 참조하세요.  <br/> |
|사용자가 Microsoft Store에서 앱을 다운로드할 수 있도록 허용  <br/> |사용자가 Microsoft Store에서 앱을 다운로드하여 설치할 수 있도록 허용합니다. 앱에는 게임에서 생산성 도구에 이르기까지 다양한 종류가 있습니다. 따라서 기본값은 **켜기**이지만 관리자가 보안을 위해 끌 수 있습니다.  <br/> |
|사용자가 Cortana에 액세스할 수 있도록 허용  <br/> |Cortana는 매우 유용한 도구입니다. Cortana는 사용자 대신 설정을 끄거나 켜고, 길을 안내해 주고, 약속을 상기시켜 줍니다. 기본값은 **켜기**입니다.  <br/> |
|사용자가 Microsoft에서 Windows 팁 및 광고를 받을 수 있도록 허용  <br/> |Windows 팁은 새로운 기능이 출시된 경우 사용자에게 이를 안내하는 등 매우 유용하게 사용됩니다.  <br/> |
|자동으로 Windows 10 장치를 최신 상태로 유지  <br/> |Windows 10 장치가 자동으로 최신 상태로 업데이트되도록 합니다.  <br/> |
|이 시간 동안 유휴 상태일 때 장치 화면 끄기  <br/> |사용자가 유휴 상태일 때 회사 데이터가 안전하게 보호되도록 합니다. 사용자가 커피숍과 같은 공공장소에서 작업하다가 잠시 자리를 비우거나 다른 곳에 주의를 기울인 순간 장치가 타인의 시선에 노출될 수 있습니다. 이 설정은 사용자가 얼마 동안 유휴 상태이면 화면이 꺼지는지 지정합니다.  <br/> |
   
  

