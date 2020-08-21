---
title: S/MIME용으로 Office 365에 사용자 인증서 동기화
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Exchange Online에서 S/MIME으로 보호되는 메시지를 전송하기 전에 Office 365에 적절한 인증서를 게시하는 방법을 알아봅니다.
ms.openlocfilehash: 634b65e45b01186a27f9ae61c91d4b27f1a11635
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826484"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>S/MIME용으로 Office 365에 사용자 인증서 동기화

Exchange Online에서 S/MIME로 보호된 메시지를 보내려면 적절한 인증서를 설정해야 합니다. Exchange Online을 통해 암호화된 메시지를 보내기 위해 보낸 사람의 전자 메일 앱은 받는 사람의 공용 인증서를 사용하여 메시지를 암호화합니다. 이 공용 X.509 인증서를 Office 365에 게시해야 합니다.

## <a name="to-sync-certificates-that-support-smime"></a>S/MIME을 지원하는 인증서를 동기화하려면

인증서를 발급하고 로컬 Active Directory 도메인 서비스에 게시하여 S/MIME 설정을 시작합니다. 자세한 내용은 [Active Directory 인증서 서비스 개요를 참조하십시오.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))

인증서를 게시한 후 Azure AD Connect 도구를 사용하여 사용자 데이터를 온-프레미스 Exchange 환경에서 Office 365로 동기화합니다. 이 프로세스에 대한 자세한 내용은 [Azure AD Connect 동기화를 참조하세요. 동기화 이해 및 사용자 지정을 참조하세요.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

이 도구는 S/MIME에 사용할 수 있도록 다른 디렉터리 데이터를 동기화하는 기능외에도 데이터를 사용하여 메시지를 서명 및 암호화할 수 있도록 각 사용자 개체에 대해  **userCertificate** 및 **UserSMIMECertificate** 특성을 동기화합니다.

## <a name="more-information"></a>추가 정보

[메시지 서명 및 암호화를 위한 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Azure AD Connect란 무엇인가요?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
