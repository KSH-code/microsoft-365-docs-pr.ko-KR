---
title: S/MIME용으로 Office 365에 사용자 인증서 동기화
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
description: S/MIME로 보호된 메시지를 보내려면 적절한 인증서를 설정해야 합니다. Exchange Online을 통해 암호화된 메시지를 보내기 위해 보낸 사람의 전자 메일 프로그램은 받는 사람의 공용 인증서를 사용하여 메시지를 암호화합니다. 이 공용 X.509 인증서를 Office 365에 게시해야 합니다.
ms.openlocfilehash: caf5c3694034f3415b42f3b09302b6605fbf09cb
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970094"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="272ff-105">S/MIME용으로 Office 365에 사용자 인증서 동기화</span><span class="sxs-lookup"><span data-stu-id="272ff-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="272ff-106">모든 사용자가 Exchange Online에서 S/MIME으로 보호 된 메시지를 보낼 수 있으려면 해당 인증서를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="272ff-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="272ff-107">Exchange Online을 통해 암호화 된 메시지를 보내기 위해 보낸 사람의 전자 메일 앱은 받는 사람의 공용 인증서를 사용 하 여 메시지를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="272ff-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="272ff-108">이 공용 X.509 인증서를 Office 365에 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="272ff-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="272ff-109">S/MIME을 지원하는 인증서를 동기화하려면</span><span class="sxs-lookup"><span data-stu-id="272ff-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="272ff-110">인증서를 발급하고 로컬 Active Directory 도메인 서비스에 게시하여 S/MIME 설정을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="272ff-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="272ff-111">자세한 내용은 [Active Directory 인증서 서비스 개요](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="272ff-111">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="272ff-112">인증서를 게시 한 후에는 Azure AD Connect 도구를 사용 하 여 온-프레미스 Exchange 환경의 사용자 데이터를 Office 365와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="272ff-112">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="272ff-113">이 프로세스에 대 한 자세한 내용은 [AZURE AD Connect 동기화: 사용자 지정 및 동기화 이해](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="272ff-113">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="272ff-114">S/MIME을 위해 다른 디렉터리 데이터를 동기화 하는 것과 함께,이 도구는 각 사용자 개체에 대 한 **userCertificate** 및 **userSMIMECertificate** 특성을 동기화 하 여 데이터를 사용 하 여 메시지를 서명 하 고 암호화 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="272ff-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="272ff-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="272ff-115">More Information</span></span>

[<span data-ttu-id="272ff-116">메시지 서명 및 암호화를 위한 S/MIME</span><span class="sxs-lookup"><span data-stu-id="272ff-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="272ff-117">Azure AD Connect 란?</span><span class="sxs-lookup"><span data-stu-id="272ff-117">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
