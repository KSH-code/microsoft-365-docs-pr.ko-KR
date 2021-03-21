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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Exchange Online에서 S/MIME으로 보호된 메시지를 보내기 전에 Office 365에 적절한 인증서를 게시하는 방법을 배우게 됩니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916457"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>S/MIME용으로 Office 365에 사용자 인증서 동기화

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online에서 S/MIME으로 보호된 메시지를 보내기 전에 적절한 인증서를 설정해야 합니다. Exchange Online을 통해 암호화된 메시지를 보내기 위해 보낸 사람의 전자 메일 앱은 받는 사람의 공용 인증서를 사용하여 메시지를 암호화합니다. 이 공용 X.509 인증서를 Office 365에 게시해야 합니다.

## <a name="to-sync-certificates-that-support-smime"></a>S/MIME을 지원하는 인증서를 동기화하려면

인증서를 발급하고 로컬 Active Directory 도메인 서비스에 게시하여 S/MIME 설정을 시작합니다. 자세한 내용은 Active Directory 인증서 서비스 [개요 를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))

인증서를 게시한 후 Azure AD Connect 도구를 사용하여 사용자 데이터를 Office 365로 동기화합니다. 이 프로세스에 대한 자세한 내용은 Azure AD Connect 동기화: 동기화 이해 및 사용자 [지정을 참조하세요.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

다른 디렉터리 데이터 동기화와 함께 S/MIME을 위해 이 도구는 각 사용자 개체의  **userCertificate** 및 **userSMIMECertificate** 특성을 동기화하여 데이터를 사용하여 메시지에 서명하고 암호화할 수 있습니다.

## <a name="more-information"></a>추가 정보

[메시지 서명 및 암호화를 위한 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Azure AD Connect란 무엇인가요?](/azure/active-directory/hybrid/whatis-azure-ad-connect)