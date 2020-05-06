---
title: S/MIME용으로 Office 365에 사용자 인증서 동기화
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Exchange Online에서 S/MIME으로 보호 된 메시지를 보내기 전에 Office 365에 적절 한 인증서를 게시 하는 방법을 알아봅니다.
ms.openlocfilehash: f9e0bef2f7d2125e2daeb86b3cf44ae433aae117
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035215"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>S/MIME용으로 Office 365에 사용자 인증서 동기화

모든 사용자가 Exchange Online에서 S/MIME으로 보호 된 메시지를 보낼 수 있으려면 해당 인증서를 설정 해야 합니다. Exchange Online을 통해 암호화 된 메시지를 보내기 위해 보낸 사람의 전자 메일 앱은 받는 사람의 공용 인증서를 사용 하 여 메시지를 암호화 합니다. 이 공용 X.509 인증서를 Office 365에 게시해야 합니다.

## <a name="to-sync-certificates-that-support-smime"></a>S/MIME을 지원하는 인증서를 동기화하려면

인증서를 발급하고 로컬 Active Directory 도메인 서비스에 게시하여 S/MIME 설정을 시작합니다. 자세한 내용은 [Active Directory 인증서 서비스 개요](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))를 참조 하세요.

인증서를 게시 한 후에는 Azure AD Connect 도구를 사용 하 여 온-프레미스 Exchange 환경의 사용자 데이터를 Office 365와 동기화 합니다. 이 프로세스에 대 한 자세한 내용은 [AZURE AD Connect 동기화: 사용자 지정 및 동기화 이해](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)를 참조 하세요.

S/MIME을 위해 다른 디렉터리 데이터를 동기화 하는 것과 함께,이 도구는 각 사용자 개체에 대 한 **userCertificate** 및 **userSMIMECertificate** 특성을 동기화 하 여 데이터를 사용 하 여 메시지를 서명 하 고 암호화 하는 데 사용할 수 있습니다.

## <a name="more-information"></a>추가 정보

[메시지 서명 및 암호화를 위한 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Azure AD Connect 란?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
