---
title: 비즈니스용 Office 클라이언트 배포를 Microsoft 365 준비
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Windows 10 컴퓨터에 32비트 Office 앱을 자동으로 설치하고 업데이트된 Windows 10 방법을 배워야 합니다.
ms.openlocfilehash: ea131e37fa7f82a0ab03aa52b71569e3c96a2c7f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186979"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>비즈니스용 Office 클라이언트 배포를 Microsoft 365 준비

이 문서는 이 문서에 Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>클라이언트 컴퓨터에 Office 앱 자동 설치 준비

32비트 Microsoft 365 Business Premium 컴퓨터에 32비트 Office 앱을 자동으로 설치하고 Windows 10 최신 앱으로 유지할 수 있습니다.
  
자동 설치는 최종 사용자의 컴퓨터가 다음 Windows 10 Business 가장 잘 작동합니다.
  
- 기존 Office 데스크톱 앱(Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, 및 OneDrive)이 없는 경우
    
    또는
    
- 기존 간편 실행 버전의 Office가 설치된 경우
    
간편 실행 버전의 Office가 있는지 확인하려는 경우 Office 앱에서 **파일** \> **계정**(Outlook에서는 **Office 계정**)으로 이동합니다. 다음 그림에 Office 업데이트가 표시되어 있는 경우 Click-to-Run을 사용하여 설치를 수행한 것입니다.  
  
![Screenshot of Office updates in Office 앱 Account.](../../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Who 기능을 사용할 경우의 이점**
  
다음과 같은 PC 환경을 사용하는 최종 사용자에게 유용합니다.
  
- **사용자** Windows 10 Business, 비즈니스용 활성 Microsoft 365 라이선스가 있으며 Windows 10 크리에이터스 업데이트 사용자 라이선스가 Azure Active Directory. 
    
- **64비트** Office(예: Word, Excel, PowerPoint). 64비트 Office 앱이 필요한 경우 비즈니스용 앱 콘솔에서 64비트 2016 Click-to-Run 버전을 트리거하는 Office 지원이 Microsoft 365 적합하지 않습니다. 
    
- 2016 Windows Installer(MSI) 독립 실행형 앱(예: Visio 또는 Project)을 **보유하지 않은** 경우. Microsoft 365 비즈니스용 업그레이드는 Office 2016의 Click-to-Run 버전으로 Office 2016 MSI 독립 실행형 Office 작동하지 않습니다. 
    
다음 표에는 비즈니스용 Microsoft 365 콘솔에서 32비트의 32비트 Click-to-Run 버전을 성공적으로 배포하기 위해 최종 사용자/관리자가 시작 상태와 관계없이 Office 수 있는 작업을 보여 줄 수 있습니다.<br/>


|Office 설치 시작 상태|비즈니스용 비즈니스 Microsoft 365 설치하기 Office 작업|최종 상태|
|:-----|:-----|:-----|
|설치된 Office 제품군이 없는 경우  <br/> |없음  <br/> |Office 사용하여 2016 32비트 설치  <br/> |
|간편 실행 32비트 버전의 Office(2016 이하)가 있고 독립 실행형 앱이 없는 경우  <br/> |없음  <br/> |Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\*** <br/> |
|기존 Click-to-Run 32비트 버전의 Office 및 32비트 또는 64비트 독립 실행형 Office 앱(예: Visio, Project)  <br/> |없음  <br/> |독립 실행형 앱은 영향을 받지 않습니다. 제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.  <br/> |
|간편 실행 32비트 버전의 Office 및 32비트 또는 64비트(2016 제외) MSI 독립 실행형 Office 앱이 있는 경우  <br/> |없음  <br/> |독립 실행형 앱은 영향을 받지 않습니다. 제품군이 간편 실행 32비트 버전의 Office 2016으로 업그레이드됩니다.  <br/> |
|간편 실행 64비트 버전의 Office가 있는 경우  <br/> |64비트 Office 앱을 32비트 앱으로 바꾸면 됩니다Office 제거  <br/> |Office 64비트 앱이 제거된 경우 간편 실행 32비트 버전의 Office 2016이 설치됩니다.  <br/> |
|독립 실행형 앱 유무와 상관없이 Office 2016의 MSI 설치가 있는 경우  <br/> |MSI Office 2016을 제거합니다.  <br/> |간편 실행 32비트 버전의 Office 2016이 설치됩니다. 독립 실행형 앱은 변경되지 않습니다.  <br/> |
|Office 2013(또는 이전 버전)의 MSI 설치 및/또는 독립 실행형 Office 앱이 있는 경우  <br/> |없음  <br/> |기존 MSI Office 설치가 포함된 간편 실행 32비트 버전의 Office 2016과 독립 실행형 앱이 함께 존재합니다.  <br/> |
||||
   
 **(\*) 참고:** 알려진 버그로 인해 간편 실행 32비트 버전의 Office 2016으로 업그레이드되지 않습니다. 수정이 진행 중입니다. 
  
