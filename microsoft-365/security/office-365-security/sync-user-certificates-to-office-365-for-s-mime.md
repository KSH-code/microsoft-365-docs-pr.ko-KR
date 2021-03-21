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
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="73377-103">S/MIME용으로 Office 365에 사용자 인증서 동기화</span><span class="sxs-lookup"><span data-stu-id="73377-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="73377-104">Exchange Online에서 S/MIME으로 보호된 메시지를 보내기 전에 적절한 인증서를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73377-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="73377-105">Exchange Online을 통해 암호화된 메시지를 보내기 위해 보낸 사람의 전자 메일 앱은 받는 사람의 공용 인증서를 사용하여 메시지를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="73377-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="73377-106">이 공용 X.509 인증서를 Office 365에 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73377-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="73377-107">S/MIME을 지원하는 인증서를 동기화하려면</span><span class="sxs-lookup"><span data-stu-id="73377-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="73377-108">인증서를 발급하고 로컬 Active Directory 도메인 서비스에 게시하여 S/MIME 설정을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="73377-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="73377-109">자세한 내용은 Active Directory 인증서 서비스 [개요 를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="73377-109">For more information, see [Active Directory Certificate Services Overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="73377-110">인증서를 게시한 후 Azure AD Connect 도구를 사용하여 사용자 데이터를 Office 365로 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="73377-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="73377-111">이 프로세스에 대한 자세한 내용은 Azure AD Connect 동기화: 동기화 이해 및 사용자 [지정을 참조하세요.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)</span><span class="sxs-lookup"><span data-stu-id="73377-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="73377-112">다른 디렉터리 데이터 동기화와 함께 S/MIME을 위해 이 도구는 각 사용자 개체의  **userCertificate** 및 **userSMIMECertificate** 특성을 동기화하여 데이터를 사용하여 메시지에 서명하고 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73377-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="73377-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="73377-113">More Information</span></span>

[<span data-ttu-id="73377-114">메시지 서명 및 암호화를 위한 S/MIME</span><span class="sxs-lookup"><span data-stu-id="73377-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="73377-115">Azure AD Connect란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="73377-115">What is Azure AD Connect?</span></span>](/azure/active-directory/hybrid/whatis-azure-ad-connect)