---
title: AD RMS를 사용하여 Exchange Online 메일 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: 조직 요구 사항을 충족하기 위해 AD RMS(Active Directory Rights Management Service)를 사용하도록 Exchange Online IRM을 구성하는 방법을 알아보십시오.
ms.openlocfilehash: 6a9759fce102c60dd766dd86ba8c9e6d4a02d85b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924992"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>AD RMS를 사용하여 Exchange Online 메일 암호화

Exchange Online에는 정보 유출을 방지하기 위해 전자 메일 메시지와 첨부 파일을 온라인과 오프라인에서 보호하는 IRM(정보 권한 관리) 기능이 포함되어 있습니다. 필요한 경우 조직 요구 사항을 충족하기 위해 Exchange Online IRM이 필요한 경우 AD RMS(Active Directory Rights Management Service)를 사용하도록 구성할 수 있습니다. 이는 일반적이지 않습니다. AD RMS를 사용할 요구 사항이 없는 경우 [대신 Office 365 메시지](ome.md) 암호화를 사용하세요. 

IRM 보호는 Microsoft Outlook 또는 웹용 Outlook의 사용자가 적용할 수 있으며, 전송 보호 규칙 또는 Outlook 보호 규칙을 사용하여 관리자가 적용할 수 있습니다. IRM을 통해 고객과 고객의 사용자는 전자 메일 내의 중요한 데이터를 액세스, 전달, 인쇄 또는 복사할 수 있는 사람을 제어할 수 있습니다.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>OME(Office 365 메시지 암호화) 및 Azure Active Directory에서 IRM이 작동하는 방식 변경 사항

2017년 9월을 기점으로 조직의 새 Office 365 메시지 암호화 기능을 설정할 때 Azure RMS(Azure 권한 관리)와 함께 사용할 IRM도 설정됩니다. 더 이상 Azure RMS를 사용하여 IRM을 별도로 설정하지 않습니다. 대신 OME와 권한 관리가 원활하게 함께 작동됩니다. 새 기능에 대한 자세한 내용은 [Office 365 메시지 암호화 FAQ 를 참조하세요.](./ome-faq.md) 조직 내에서 새로운 OME 기능을 사용할 준비가 된 경우 Azure Information Protection을 토대하여 구축된 새 Office 365 메시지 암호화 기능 [설치를 참조하세요.](./set-up-new-message-encryption-capabilities.md)
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Exchange Online 및 Exchange Online에서 IRM이 작동하는 Active Directory Rights Management Services

Exchange Online IRM은 Windows Server 2008 Active Directory Rights Management Services의 정보 보호 기술인 AD RMS(On-premises Active Directory Rights Management Services)를 사용 합니다. AD RMS 권한 정책 템플릿을 전자 메일 메시지에 적용하여 전자 메일에 IRM 보호를 적용합니다. 조직 방화벽 내부와 외부에서 온라인 및 오프라인으로 보호가 진행할 수 있도록 메시지 자체에 권한이 첨부됩니다.
  
사용자는 전자 메일 메시지에 서식 파일을 적용하여 받는 사람이 메시지에 대한 사용 권한을 제어할 수 있습니다. 즉, 메시지에 AD RMS 권한 정책을 적용하여 전달, 메시지에서 정보 추출, 메시지 저장 또는 메시지 인쇄 등의 작업을 제어할 수 있습니다.
  
Windows Server 2008 이상을 실행하는 AD RMS 서버를 사용하도록 IRM을 구성할 수 있습니다. 이 AD RMS 서버를 사용하여 클라우드 기반 조직에 대한 AD RMS 권한 정책 템플릿을 관리합니다. 또한 Outlook에서는 AD RMS 서버를 사용하여 사용자가 자신이 보낸 메시지에 IRM 보호를 적용할 수 있도록 합니다. 자세한 내용은 [Configure IRM to use an on-premises AD RMS server을 참조하세요.](configure-irm-to-use-an-on-premises-ad-rms-server.md) 
  
IRM을 사용하도록 설정한 후에는 다음과 같이 메시지에 IRM 보호를 적용할 수 있습니다.
  
- **사용자는 Outlook 및 웹용 Outlook을 사용하여 템플릿을 수동으로 적용할 수 있습니다.** 사용자는 **사용 권한 설정** 목록에서 AD RMS 권한 정책 템플릿을 선택하여 전자 메일 메시지에 적용할 수 있습니다. 사용자가 IRM으로 보호된 메시지를 보내는 경우 지원되는 형식을 사용하는 첨부된 파일에도 메시지와 같은 IRM 보호가 적용됩니다. IRM 보호는 .xps 파일 및 첨부된 전자 메일 메시지는 물론 Word, Excel 및 PowerPoint와 연결된 파일에도 적용됩니다. 
    
- **관리자는 전송 보호 규칙을 사용하여 Outlook과 웹용 Outlook 모두에 IRM 보호를 자동으로 적용할 수 있습니다.** IRM 보호 메시지에 대한 전송 보호 규칙을 만들 수 있습니다. 규칙 조건에 맞는 메시지에 AD RMS 권한 정책 템플릿을 적용하도록 전송 보호 규칙 동작을 구성합니다. IRM을 사용하도록 설정하고 나면 조직의 AD RMS 권한 정책 템플릿을 **다음을 포함하는 메시지에 권한 보호 적용** 이라는 전송 보호 규칙 동작과 함께 사용할 수 있게 됩니다.
    
- **관리자는 Outlook 보호 규칙을 만들 수 있습니다.** Outlook 보호 규칙은 보낸 사람의 부서, 메시지를 받는 사람 및 받는 사람이 조직 내부 또는 외부에 있는지 여부가 포함된 메시지 조건에 따라 Outlook 2010의 메시지(웹용 Outlook 아미지)에 IRM 보호를 자동으로 적용합니다. 자세한 내용은 [Create an Outlook Protection Rule](/exchange/create-an-outlook-protection-rule-exchange-2013-help)를 참조하십시오.
