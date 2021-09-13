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
description: 이 Office 365 일부 암호화 기능은 기본적으로 켜져 있습니다. 특정 규정 준수 또는 법적 요구 사항을 충족하도록 다른 기능을 구성할 수 있습니다.
ms.openlocfilehash: a9a3170fdb99a4acfec8cf4d3b03ab9b584197bd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216385"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Office 365 Enterprise의 암호화 설정

암호화는 권한이 없는 사용자가 콘텐츠를 읽지 못하게 보호할 수 있습니다. 여러 기술 및 [Office 365](encryption.md) 사용하여 암호화를 할 수 있기 때문에 암호화를 설정하거나 설정하는 한 위치는 없습니다. 이 문서에서는 정보 보호 전략의 일부로 암호화를 설정하거나 구성할 수 있는 다양한 방법에 대한 정보를 제공합니다.

> [!TIP]
> 암호화에 대한 자세한 기술 세부 정보를 찾고 있는 경우 에서 암호화에 대한 기술 참조 [세부 Office 365.](technical-reference-details-about-encryption.md)

이 Office 365 기본적으로 여러 암호화 기능을 사용할 수 있습니다. 특정 규정 준수 또는 법적 요구 사항을 충족하도록 추가 암호화 기능을 구성할 수 있습니다. 다음 표에서는 다양한 시나리오에 대한 여러 암호화 방법에 대해 설명합니다.

<br>

****

|시나리오|암호화 방법|
|---|---|
|파일이 컴퓨터의 Windows 저장됩니다.|컴퓨터 수준의 암호화는 디바이스에서 BitLocker를 사용하여 Windows 있습니다. 엔터프라이즈 관리자 또는 IT Pro MDT(Microsoft Deployment Toolkit 사용하여 설정할 수 있습니다. [BitLocker에 대한 MDT 설정 을 참조합니다.](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)|
|파일이 모바일 장치에 저장됩니다.|일부 종류의 모바일 장치는 기본적으로 해당 장치에 저장되는 파일을 암호화합니다. 기본 [제공](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)Office 365용 모바일 장치 관리 를 사용하여 모바일 장치가 모바일 장치의 데이터에 액세스할 수 있도록 허용할지 여부를 결정하는 정책을 설정할 수 Office 365. 예를 들어 콘텐츠를 암호화하는 장치만 해당 데이터에 액세스할 수 있도록 허용하는 정책을 Office 365 있습니다. 장치 [보안 정책 만들기 및 배포를 참조하세요.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6) <p> 모바일 장치가 모바일 장치와 상호 작용하는 방식을 추가로 Office 365 를 추가하는 [Microsoft Intune.](/mem/intune/fundamentals/setup-steps)|
|Microsoft 데이터 센터에서 데이터를 암호화하는 데 사용되는 암호화 키를 제어해야 합니다.|관리자는 Office 365 조직의 암호화 키를 제어한 다음 Microsoft 데이터 센터의 Office 365 데이터를 암호화하는 데 사용하도록 구성할 수 있습니다. <p> [Office 365의 고객 키를 사용한 서비스 암호화](customer-key-overview.md)|
|전자 메일을 통해 통신하는 사용자(Exchange Online)|관리자의 Exchange Online 전자 메일 암호화를 구성하는 데 사용할 수 있는 몇 가지 옵션이 있습니다. 다음이 포함되어 있습니다. <ul><li>[OME(Office 365 암호화)를](set-up-new-message-encryption-capabilities.md) Azure RMS(권한 관리)와 함께 사용하여 조직 내부 또는 외부에서 암호화된 메시지를 보낼 수 있도록 합니다.</li><li>[S/MIME을](/exchange/security-and-compliance/smime-exo/smime-exo) 사용하여 전자 메일 메시지 암호화 및 디지털 서명</li><li>TLS를 사용하여 다른 조직과의 보안 메일 [흐름을 위한 커넥터 설정](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> 에서 [전자 메일 암호화를 Office 365.](./email-encryption.md)|
|파일 액세스는 팀 사이트 또는 문서 라이브러리(비즈니스용 OneDrive 또는 SharePoint Online)에서 액세스됩니다.|사용자가 온라인 또는 비즈니스용 OneDrive 파일로 작업하는 SharePoint TLS 연결이 사용됩니다. 이 설정은 자동으로 Office 365 기본 제공됩니다. 온라인 [비즈니스용 OneDrive 및 SharePoint 암호화를 참조하세요.](./data-encryption-in-odb-and-spo.md)|
|온라인 모임 및 IM 대화에서 파일이 공유됩니다(비즈니스용 Skype Online).|사용자가 비즈니스용 Skype 사용하여 파일을 작업하는 경우 연결에 TLS가 사용됩니다. 이 설정은 자동으로 Office 365 기본 제공됩니다. 보안 [및 보관(비즈니스용 Skype Online)을 참조하세요.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)|
|온라인 모임 및 IM 대화에서 파일이 공유됩니다(Microsoft Teams)|사용자가 파일을 사용하여 작업하는 Microsoft Teams 연결에 TLS가 사용됩니다. 이 설정은 자동으로 Office 365 기본 제공됩니다. Microsoft Teams 현재 암호화된 전자 메일의 인라인 렌더링을 지원하지 않습니다. 암호화된 전자 메일이 암호화된 전자 메일로 Microsoft Teams 수 없습니다. 메시지 암호화 [FAQ를 참조하세요.](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)|
|

## <a name="additional-information"></a>추가 정보

암호화 옵션이 포함된 파일 보호 솔루션에 대한 자세한 내용은 File [Protection Solutions in Office 365.](https://www.microsoft.com/download/details.aspx?id=55523)
