---
title: 가상 인증서 컬렉션 설정 - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 관리자는 Exchange Online에서 S/MIME 인증서의 유효성을 검사하는 데 사용할 가상 인증서 컬렉션을 만드는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916659"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="de5ac-103">S/MIME의 유효성을 검사하기 위해 Exchange Online에서 가상 인증서 컬렉션 설정</span><span class="sxs-lookup"><span data-stu-id="de5ac-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="de5ac-104">관리자는 S/MIME 인증서의 유효성을 검사하는 데 사용할 가상 인증서 컬렉션을 Exchange Online에서 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ac-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="de5ac-105">이 가상 인증서 컬렉션은 SST 파일 이름 확장명을 통해 인증서 저장소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5ac-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="de5ac-106">SST 파일에는 S/MIME 인증서 유효성을 검사할 때 사용되는 모든 루트 및 중간 인증서가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5ac-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="de5ac-107">SST 만들기 및 저장</span><span class="sxs-lookup"><span data-stu-id="de5ac-107">Create and save an SST</span></span>

<span data-ttu-id="de5ac-108">이 SST 인증서 저장소 파일은 신뢰할 수 있는 컴퓨터의 **Export-Certificate** cmdlet을 사용하여 내보내고 Windows PowerShell  값을 SST로 지정하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ac-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="de5ac-109">자세한 내용은 [Export-Certificate를 참조하세요.](/powershell/module/pkiclient/export-certificate)</span><span class="sxs-lookup"><span data-stu-id="de5ac-109">For instructions, see [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="de5ac-110">SST 인증서 저장소 파일이 있는 경우 Exchange Online PowerShell에서 다음 구문을 사용하여 SST 파일 콘텐츠를 Exchange Online 가상 인증서 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="de5ac-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="de5ac-111">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de5ac-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="de5ac-112">이 예제에서는 SST 파일 C:\My Documents\Exported Certificate Store.sst를 가져오습니다.</span><span class="sxs-lookup"><span data-stu-id="de5ac-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="de5ac-113">구문과 매개 변수에 대한 자세한 내용은 [Set-SmimeConfig 를 참조하십시오.](/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="de5ac-113">For detailed syntax and parameter information, see [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="de5ac-114">인증서가 유효한지 확인</span><span class="sxs-lookup"><span data-stu-id="de5ac-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="de5ac-115">Exchange Online에서는 SST만 인증서 유효성 검사에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5ac-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="de5ac-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="de5ac-116">More Information</span></span>

[<span data-ttu-id="de5ac-117">메시지 서명 및 암호화를 위한 S/MIME</span><span class="sxs-lookup"><span data-stu-id="de5ac-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="de5ac-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="de5ac-118">Get-SmimeConfig</span></span>](/powershell/module/exchange/get-smimeconfig)