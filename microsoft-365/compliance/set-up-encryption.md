---
title: Office 365 Enterprise의 암호화 설정
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Office 365에서는 일부 암호화 기능이 기본적으로 켜져 있습니다. 다른 기능은 특정 규정 준수 또는 법적 요구 사항을 충족하도록 구성할 수 있습니다.
ms.openlocfilehash: 268bd7b57884549b7ab4abb45a7b69485498f1cb
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44799993"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Office 365 Enterprise의 암호화 설정

암호화는 권한이 없는 사용자가 콘텐츠를 읽지 못하게 보호할 수 있습니다. [Office 365의](encryption.md) 암호화는 다양한 기술 및 방법을 사용하여 수행될 수 있기 때문에 암호화를 설정하거나 설정하는 단일 위치는 없습니다. 이 문서에서는 정보 보호 전략의 일부로 암호화를 설정하거나 구성할 수 있는 다양한 방법에 대한 정보를 제공합니다.
  
> [!TIP]
> 암호화에 대한 자세한 기술 정보를 찾고 있는 경우 [Office 365의](technical-reference-details-about-encryption.md)암호화에 대한 기술 참조 세부 정보를 참조하세요.
  
Office 365에서는 기본적으로 여러 암호화 기능을 사용할 수 있습니다. 특정 규정 준수 또는 법적 요구 사항을 충족하도록 추가 암호화 기능을 구성할 수 있습니다. 다음 표에서는 여러 시나리오에 대한 여러 암호화 방법에 대해 설명합니다.
  
|**시나리오**|**암호화 방법**|
|:-----|:-----|
|파일이 Windows 컴퓨터에 저장됩니다.  <br/> |컴퓨터 수준에서 암호화는 Windows 장치에서 BitLocker를 사용하여 수행될 수 있습니다. 엔터프라이즈 관리자 또는 IT Pro는 MDT(Microsoft Deployment Toolkit)를 사용하여 설정할 수 있습니다. [BitLocker에 대한 MDT 설정을 참조합니다.](https://go.microsoft.com/fwlink/?linkid=849282)  <br/> |
|파일이 모바일 장치에 저장됩니다.  <br/> |일부 종류의 모바일 장치는 기본적으로 해당 장치에 저장되는 파일을 암호화합니다. Office 365에 대한 기본 제공 모바일 장치 관리 기능을 사용하여 모바일 장치가 [Office 365의](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)데이터에 액세스할 수 있도록 허용할지 여부를 결정하는 정책을 설정할 수 있습니다. 예를 들어 콘텐츠를 암호화하는 장치만 Office 365 데이터에 액세스할 수 있도록 하는 정책을 설정할 수 있습니다. 장치 보안 정책 만들기 [및 배포를 참조하세요.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)  <br/> 모바일 장치가 Office 365와 상호 작용하는 방식을 추가로 제어하기 위해 [Microsoft Intune을 추가하는 것을 고려할 수 있습니다.](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps)  <br/> |
|Microsoft 데이터 센터에서 데이터를 암호화하는 데 사용되는 암호화 키를 제어해야 합니다.  <br/> | Office 365 관리자는 조직의 암호화 키를 제어한 다음 Office 365를 구성하여 Microsoft 데이터 센터의 미사용 데이터를 암호화할 수 있습니다.  <br/> [Office 365의 고객 키를 사용한 서비스 암호화](customer-key-overview.md) <br/> |
|전자 메일을 통해 통신하는 사용자(Exchange Online)  <br/> | Exchange Online 관리자는 전자 메일 암호화를 구성하기 위한 몇 가지 옵션을 사용할 수 있습니다. 여기에는 다음이 포함됩니다.  <br/>  사용자가 조직 내부 또는 외부에서 암호화된 메시지를 보낼 수 있도록 Azure RMS(Azure 권한 관리)와 함께 [OME(Office 365](set-up-new-message-encryption-capabilities.md) 메시지 암호화)를 사용합니다.  <br/>  메시지 서명 및 암호화에 [S/MIME를 사용하여](https://aka.ms/c6dozg) 전자 메일 메시지 암호화 및 디지털 서명  <br/>  TLS를 사용하여 다른 조직과의 보안 메일 [흐름을](https://aka.ms/hs809p) 위한 커넥터 설정 <br/>  [Office 365에서 전자 메일 암호화를 참조하세요.](https://aka.ms/hic3f7)  <br/> |
|팀 사이트 또는 문서 라이브러리에서 파일에 액세스합니다(비즈니스용 OneDrive 또는 SharePoint Online)  <br/> |사용자가 비즈니스용 OneDrive 또는 SharePoint Online에 저장된 파일로 작업하는 경우 TLS 연결이 사용됩니다. 이는 Office 365에 자동으로 기본 제공됩니다. 비즈니스용 [OneDrive 및 SharePoint Online에서 데이터 암호화를 참조하세요.](https://go.microsoft.com/fwlink/?linkid=526379)  <br/> |
|온라인 모임 및 IM 대화에서 파일이 공유됩니다(비즈니스용 Skype Online)  <br/> |사용자가 비즈니스용 Skype Online을 사용하여 파일을 작업하는 경우 연결에 TLS가 사용됩니다. Office 365에서 자동으로 기본 제공됩니다. 보안 [및 보관(비즈니스용 Skype Online)을 참조하세요.](https://aka.ms/nuq4ws)  <br/> |
|온라인 모임 및 IM 대화에서 파일이 공유됩니다(Microsoft Teams).  <br/> |사용자가 Microsoft Teams를 사용하여 파일을 작업할 때 연결에 TLS가 사용됩니다. 이는 Office 365에 자동으로 기본 제공됩니다. Microsoft Teams는 현재 암호화된 전자 메일의 인라인 렌더링을 지원하지 않습니다. 암호화된 전자 메일이 암호화된 Microsoft Teams에 전송되지 않도록 방지하는 경우 메시지 암호화 [FAQ를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/ome-faq?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)  <br/> 

## <a name="additional-information"></a>추가 정보

암호화 옵션이 포함된 파일 보호 솔루션에 대한 자세한 내용은 [Office 365의 파일 보호 솔루션을 참조하세요.](https://www.microsoft.com/download/details.aspx?id=55523)
 
