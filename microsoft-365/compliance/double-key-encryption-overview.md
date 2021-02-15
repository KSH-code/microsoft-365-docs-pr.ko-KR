---
title: 이중 키 암호화 개요 및 FAQ
description: Microsoft 365의 이중 키 암호화에 대한 질문과 대답
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 32686e76018d8b6a361ea99e6b00271b9547ed95
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663063"
---
# <a name="double-key-encryption-frequently-asked-questions"></a><span data-ttu-id="ed4d3-103">이중 키 암호화 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="ed4d3-103">Double Key Encryption frequently asked questions</span></span>

<span data-ttu-id="ed4d3-104">이중 키 암호화의 작동 방식에 대해 질문이 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-104">Have a question about how Double Key Encryption works?</span></span> <span data-ttu-id="ed4d3-105">여기에서 답변을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-105">Check for an answer here.</span></span>

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a><span data-ttu-id="ed4d3-106">Microsoft 365(DKE)의 이중 키 암호화란?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-106">What is Double Key Encryption for Microsoft 365 (DKE)?</span></span>

<span data-ttu-id="ed4d3-107">Microsoft 365의 이중 키 암호화를 통해 고객은 특수한 요구 사항을 충족하기 위해 매우 중요한 데이터를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-107">Double Key Encryption for Microsoft 365 enables customers to protect their highly sensitive data to meet specialized requirements.</span></span> <span data-ttu-id="ed4d3-108">이는 고객이 암호화 키에 대한 모든 제어를 유지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-108">It helps customers maintain full control of their encryption keys.</span></span> <span data-ttu-id="ed4d3-109">두 개의 키를 사용하여 데이터를 보호합니다. 컨트롤의 키 한 개와 Microsoft Azure에 안전하게 저장된 두 번째 키</span><span class="sxs-lookup"><span data-stu-id="ed4d3-109">It uses two keys to protect data; one key in your control and a second key stored securely in Microsoft Azure.</span></span> <span data-ttu-id="ed4d3-110">이중 키 암호화로 보호된 데이터를 보는 경우 두 키에 모두 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-110">Viewing data protected with Double Key Encryption requires access to both keys.</span></span> <span data-ttu-id="ed4d3-111">Microsoft는 이러한 키 중 하나에만 액세스할 수 있으며 보호된 데이터는 Microsoft에 액세스할 수 없는 상태로 유지하여 데이터 개인 정보 및 보안을 모든 권한이 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-111">Since Microsoft can access only one of these keys, protected data remains inaccessible to Microsoft, ensuring that you have full control over your data privacy and security.</span></span>  

<span data-ttu-id="ed4d3-112">키를 요청하는 데 사용되는 이중 키 암호화 서비스를 원하는 위치(프레미스 키 관리 서버 또는 클라우드)에서 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-112">You can host the Double Key Encryption service used to request your key, in a location of your choice (on-premises key management server or in the cloud).</span></span> <span data-ttu-id="ed4d3-113">다른 응용 프로그램과 같은 서비스도 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-113">You maintain the service as you would any other application.</span></span> <span data-ttu-id="ed4d3-114">이중 키 암호화를 사용하면 이중 키 암호화 서비스에 대한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-114">Double Key Encryption enables you to control access to the Double Key Encryption service.</span></span> <span data-ttu-id="ed4d3-115">매우 중요한 데이터를 프레미스에 저장하거나 클라우드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-115">You can store your highly sensitive data on-premises or move it to the cloud.</span></span> <span data-ttu-id="ed4d3-116">키에 대한 모든 권한을 유지 관리하기 때문에 타사 액세스를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-116">You can be confident about preventing third-party access because you maintain full control of your key.</span></span> <span data-ttu-id="ed4d3-117">이중 키 암호화를 사용하면 데이터와 키를 같은 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-117">Double Key Encryption allows you to store your data and key in the same location.</span></span>

<span data-ttu-id="ed4d3-118">DKE는 GDPR(일반 데이터 보호 규정), HIPAA(Health Insurance Portability and Accountability Act), GLBA(Gramm-Leach-Bliley Act), 러시아의 데이터 지역화 법률 - 연방법 No와 같은 여러 규정 및 표준에 대한 규정 요구 사항을 충족할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-118">DKE helps you meet regulatory requirements across several regulations and standards such as the General Data Protection Regulation (GDPR), the Health Insurance Portability and Accountability Act (HIPAA), the Gramm-Leach-Bliley Act (GLBA), Russia’s data localization law – Federal Law No.</span></span> <span data-ttu-id="ed4d3-119">242-FZ, 오스트레일리아 연방 개인 정보 보호법 1988 및 뉴질랜드 개인 정보 보호법 1993.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-119">242-FZ, Australia’s Federal Privacy Act 1988, and New Zealand’s Privacy Act 1993.</span></span>

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a><span data-ttu-id="ed4d3-120">기본 제공 민감도 레이블 지정과 함께 Microsoft Office 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-120">Can I use Double Key Encryption with Microsoft Office built-in sensitivity labeling?</span></span>

<span data-ttu-id="ed4d3-121">Azure Information Protection 통합 레이블 클라이언트를 사용하여 이중 키 암호화로 문서를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-121">You'll need to use the Azure Information Protection unified labeling client to protect documents with Double Key Encryption.</span></span> <span data-ttu-id="ed4d3-122">현재는 기본 제공 민감도 Microsoft Office 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-122">Currently, you can't use Microsoft Office built-in sensitivity labeling.</span></span>

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a><span data-ttu-id="ed4d3-123">DKE와 함께 어떤 Microsoft 365 앱을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-123">What Microsoft 365 Apps can I use with DKE?</span></span>

<span data-ttu-id="ed4d3-124">DKE 레이블을 사용하여 Windows에서 데스크톱 버전의 Word, Excel 및 PowerPoint를 사용하여 문서를 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-124">You can use DKE labels to protect documents using the desktop versions of Word, Excel, and PowerPoint on Windows.</span></span> <span data-ttu-id="ed4d3-125">Windows에서 \*.12711 이상(데스크톱 버전의 Word, PowerPoint 및 Excel)을 사용하고 있습니까?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-125">Ensure that you're using \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a><span data-ttu-id="ed4d3-126">이중 키 암호화는 기존 HYOK(키 보유) 솔루션과 어떻게 다른가요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-126">How is Double Key Encryption different from the existing hold your own key (HYOK) solution?</span></span>

<span data-ttu-id="ed4d3-127">이중 키 암호화는 두 개의 키로 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-127">Double Key Encryption encrypts your data with two keys.</span></span> <span data-ttu-id="ed4d3-128">암호화 키는 제어에 있으며 두 번째 키는 Microsoft Azure에 저장되므로 암호화된 데이터를 클라우드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-128">Your encryption key is in your control and the second key is stored in Microsoft Azure, allowing you to move your encrypted data to the cloud.</span></span> <span data-ttu-id="ed4d3-129">HYOK는 키가 하나만 있는 콘텐츠를 보호하며 키는 항상 프레미스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-129">HYOK protects your content with only one key and the key is always on premises.</span></span>  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a><span data-ttu-id="ed4d3-130">이중 키로 암호화된 문서를 외부에서 공유할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-130">Can Double Key Encrypted documents be shared externally?</span></span>

<span data-ttu-id="ed4d3-131">다음 사용자에 한해 이중 키로 암호화된 문서를 별도의 테넌트의 사용자와 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-131">You can share Double Key Encrypted documents with users on a separate tenant as long as those users:</span></span>

- <span data-ttu-id="ed4d3-132">이중 키 암호화 서비스의 키에 액세스하는 데 필요한 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-132">Have the required permission to access your key in your Double Key Encryption service.</span></span>

- <span data-ttu-id="ed4d3-133">Microsoft Azure에서 키에 액세스하는 데 필요한 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-133">Have the required permission to access your key in Microsoft Azure.</span></span>

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a><span data-ttu-id="ed4d3-134">HYOK로 보호되는 문서는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-134">What happens to documents that are protected with HYOK?</span></span>

<span data-ttu-id="ed4d3-135">이중 키 암호화를 배포하면 기존 HYOK 설정에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-135">Deploying Double Key Encryption won't affect your existing HYOK setup.</span></span> <span data-ttu-id="ed4d3-136">그러나 HYOK와 동시에 이중 키 암호화를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-136">However, we recommend that you start using Double Key Encryption in parallel with HYOK.</span></span>

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a><span data-ttu-id="ed4d3-137">Microsoft가 아닌 다른 환경에서 이중 키 암호화를 실행할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-137">Can I run Double Key Encryption in my non-Microsoft air-gapped environment?</span></span>

<span data-ttu-id="ed4d3-138">서비스가 Microsoft Azure에 액세스해야 하기 때문에 DKE는 이러한 환경을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-138">DKE doesn't support these environments because the service requires access to Microsoft Azure.</span></span>

## <a name="where-can-i-store-double-key-encrypted-documents"></a><span data-ttu-id="ed4d3-139">Double Key Encrypted 문서는 어디에서 저장할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-139">Where can I store Double Key Encrypted documents?</span></span>

<span data-ttu-id="ed4d3-140">이중 키로 암호화된 문서를 On-premises 또는 클라우드에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-140">You can store Double Key Encrypted documents on-premises or in the cloud.</span></span> <span data-ttu-id="ed4d3-141">클라우드에서 암호화된 콘텐츠를 SharePoint Online 및 비즈니스용 OneDrive로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-141">In the cloud, you can move encrypted content to SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="ed4d3-142">Microsoft는 개인 키에 액세스할 수 없습니다. 암호화된 데이터는 Microsoft에 불투명하게 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-142">Since Microsoft doesn't have access to your private key, the encrypted data remains opaque to Microsoft.</span></span> <span data-ttu-id="ed4d3-143">즉, Office Web Apps에서 온라인으로 암호화된 문서를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-143">This also means that you can't view the encrypted documents online in Office Web Apps.</span></span>

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a><span data-ttu-id="ed4d3-144">이중 키 암호화를 사용할 수 있는 지역 및 언어는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-144">What regions and languages is Double Key Encryption available in?</span></span> <span data-ttu-id="ed4d3-145">전 세계에 이중 키 암호화를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-145">Is Double Key Encryption available worldwide?</span></span>

<span data-ttu-id="ed4d3-146">DKE 레이블은 Microsoft Information Protection의 다른 민감도 레이블과 동일한 언어로 지역화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-146">DKE labels are localized to the same languages as other sensitivity labels in Microsoft Information Protection.</span></span> <span data-ttu-id="ed4d3-147">이중 키 암호화는 전 세계에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-147">Double Key Encryption is available worldwide.</span></span>

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a><span data-ttu-id="ed4d3-148">DKE가 아닌 레이블을 DKE 레이블로 변환할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed4d3-148">Can I convert a non-DKE label to a DKE label?</span></span>

<span data-ttu-id="ed4d3-149">아니요.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-149">No.</span></span> <span data-ttu-id="ed4d3-150">만든 레이블에는 DKE를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-150">You can’t add DKE to a label after you create it.</span></span> <span data-ttu-id="ed4d3-151">대신 이중 키  암호화 사용을 선택하고 레이블을 만들 때 이중 키 암호화 서비스의 URL을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-151">Instead, you must choose **Use Double Key Encryption** and provide the URL of your Double Key Encryption service when you create the label.</span></span>

## <a name="how-do-i-roll-my-dke-keys"></a><span data-ttu-id="ed4d3-152">DKE 키를 롤링하는 방법</span><span class="sxs-lookup"><span data-stu-id="ed4d3-152">How do I roll my DKE keys?</span></span>

<span data-ttu-id="ed4d3-153">Azure에 저장하는 키의 롤링(회전 또는 키라고도 불리)에 대한 지침은 Azure Information Protection 테넌트 키에 대한 [작업(Operations)을 참조하세요.](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)</span><span class="sxs-lookup"><span data-stu-id="ed4d3-153">For instructions on rolling (also called rotating or rekeying) the key you store in Azure, see [Operations for your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key).</span></span>

<span data-ttu-id="ed4d3-154">DKE 서비스의 새 [키를](double-key-encryption.md#tenant-and-key-settings) 만드는 데 대한 자세한 내용은 테넌트 및 키 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-154">See [Tenant and key settings](double-key-encryption.md#tenant-and-key-settings) for information on creating a new key for the DKE service.</span></span>

<span data-ttu-id="ed4d3-155">키를 만들 때 이름과 GUID를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-155">When you create a key, you set up a name and a GUID.</span></span> <span data-ttu-id="ed4d3-156">그런 다음 키를 회전하면 이름과 GUID가 있는 이전 레코드를 유지하지만 이름이 같지만 GUID가 다른 새 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-156">Then, if you rotate a key, you keep the old record with the name and GUID but add a new record with the same name but different GUID.</span></span> <span data-ttu-id="ed4d3-157">새 키는 활성으로 설정되어 공개 키 API가 새 암호화를 위해 반환하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-157">The new key gets set as active so that the public key API starts returning it for new encryption.</span></span> <span data-ttu-id="ed4d3-158">새 콘텐츠와 이전 콘텐츠의 암호를 해독할 수 있도록 두 키를 모두 암호 해독에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed4d3-158">Both keys are available for decryption so that new content and old content can be decrypted.</span></span>
