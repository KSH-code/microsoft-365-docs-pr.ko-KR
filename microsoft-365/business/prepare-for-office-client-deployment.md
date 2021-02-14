---
title: 비즈니스용 Microsoft 365의 Office 클라이언트 배포 준비
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Windows 10 컴퓨터에 32비트 Office 앱을 자동으로 설치하고 업데이트된 것으로 유지하는 방법을 알아보고 있습니다.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470950"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>비즈니스용 Microsoft 365의 Office 클라이언트 배포 준비

이 문서는 Microsoft 365 Business Premium에 적용됩니다.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>클라이언트 컴퓨터에 Office 앱 자동 설치 준비

Microsoft 365 Business Premium을 사용하여 Windows 10 컴퓨터에 32비트 Office 앱을 자동으로 설치하고 최신 업데이트로 유지할 수 있습니다.
  
자동 설치는 최종 사용자의 컴퓨터가 Windows 10 Business에 있는 경우 가장 잘 작동합니다.
  
- 기존 Office 데스크톱 앱(Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, 및 OneDrive)이 없는 경우
    
    또는
    
- 기존 간편 실행 버전의 Office가 설치된 경우
    
간편 실행 버전의 Office가 있는지 확인하려는 경우 Office 앱에서 **파일** \> **계정**(Outlook에서는 **Office 계정**)으로 이동합니다. 다음 그림에 **표시된 Office 업데이트가** 표시된 경우 설치가 클릭하여 실행을 통해 수행된 것입니다. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **이 기능을 사용하면 이점이 있는 사람**
  
다음과 같은 PC 환경을 사용하는 최종 사용자에게 유용합니다.
  
-  Windows 10 Business 사용자 라이선스, 활성 비즈니스용 Microsoft 365 라이선스, Windows 10 크리에이터스 업데이트가 있으며 Azure Active Directory에 가입되어 있습니다. 
    
-  64비트 Office 앱이 없습니다(예: Word, Excel, PowerPoint). 64비트 Office 앱이 필요한 경우 비즈니스용 Microsoft 365 관리 콘솔에서 64비트 2016 Click-to-Run 버전의 Office를 트리거할 수 있기 때문에 이 기능이 적합하지 않습니다. 
    
- 2016 Windows Installer(MSI) 독립 실행형 앱(예: Visio 또는 Project)을 **보유하지 않은** 경우. 비즈니스용 Microsoft 365는 Office를 Click-to-Run 버전의 Office 2016으로 업그레이드하며 Office 2016 MSI 독립 실행형 앱에서는 작동하지 않습니다. 
    
다음 표에서는 비즈니스용 Microsoft 365 관리 콘솔에서 32비트의 Click-to-Run 버전의 Office 배포를 성공적으로 수행하기 위해 최종 사용자/관리자가 시작 상태에 따라 취해야 할 수 있는 작업을 보여줍니다.
  
|**Office 설치 시작 상태**|**비즈니스용 Microsoft 365 Office 설치 전에 취할 작업**|**종료 상태**|
|:-----|:-----|:-----|
|설치된 Office 제품군이 없는 경우  <br/> |없음  <br/> |Click-to-Run을 사용하여 Office 2016 32비트가 설치됩니다.  <br/> |
|간편 실행 32비트 버전의 Office(2016 이하)가 있고 독립 실행형 앱이 없는 경우  <br/> |없음  <br/> |Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\*** <br/> |
|기존 Click-to-Run 32비트 버전의 Office 및 Click-to-Run 32비트 또는 64비트 독립 실행형 Office 앱(예: Visio, Project)  <br/> |없음  <br/> |독립 실행형 앱은 영향을 받지 않습니다. 제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.  <br/> |
|간편 실행 32비트 버전의 Office 및 32비트 또는 64비트(2016 제외) MSI 독립 실행형 Office 앱이 있는 경우  <br/> |없음  <br/> |독립 실행형 앱은 영향을 받지 않습니다. 제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.  <br/> ||||
|간편 실행 64비트 버전의 Office가 있는 경우  <br/> |32비트 Office 앱으로 바꾸는 것이 괜찮은 경우 64비트 Office 앱 제거  <br/> |Office 64비트 앱이 제거된 경우 간편 실행 32비트 버전의 Office 2016이 설치됩니다.  <br/> |
|독립 실행형 앱 유무와 상관없이 Office 2016의 MSI 설치가 있는 경우  <br/> |MSI Office 2016을 제거합니다.  <br/> |간편 실행 32비트 버전의 Office 2016이 설치됩니다. 독립 실행형 앱은 변경되지 않습니다.  <br/> |
|Office 2013(또는 이전 버전)의 MSI 설치 및/또는 독립 실행형 Office 앱이 있는 경우  <br/> |없음  <br/> |기존 MSI Office 설치가 포함된 간편 실행 32비트 버전의 Office 2016과 독립 실행형 앱이 함께 존재합니다.  <br/> |
||||
   
 **(\*) 참고:** 알려진 버그로 인해 간편 실행 32비트 버전의 Office 2016으로 업그레이드되지 않습니다. 수정이 진행 중입니다. 
  
