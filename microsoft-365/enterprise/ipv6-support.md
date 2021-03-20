---
title: Office 365 서비스의 IPv6 지원
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: '요약: Microsoft Office 365 구성 요소 및 Office 365 정부 제품에서 IPv6 지원을 설명하는 문서입니다.'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909685"
---
# <a name="ipv6-support-in-office-365-services"></a><span data-ttu-id="98834-103">Office 365 서비스의 IPv6 지원</span><span class="sxs-lookup"><span data-stu-id="98834-103">IPv6 support in Office 365 services</span></span>

<span data-ttu-id="98834-104">*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="98834-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="98834-105">Office 365는 IPv6 및 IPv4를 모두 지원합니다. 그러나 일부 Office 365 기능은 IPv6에서 완전히 사용하도록 설정되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-105">Office 365 supports both IPv6 and IPv4; however, not all Office 365 features are fully enabled with IPv6.</span></span> <span data-ttu-id="98834-106">즉, IPv4 및 IPv6을 모두 사용하여 Office 365에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-106">This means that you must use both IPv4 and IPv6 to connect to Office 365.</span></span> <span data-ttu-id="98834-107">Office 365로의 아웃바운드 트래픽을 필터링하는 경우 Office 365에서 지원하는 IPv6 주소의 전체 목록은 [Office 365 URL](urls-and-ip-address-ranges.md)및 IP 주소 범위 문서에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-107">If you are filtering your outbound traffic to Office 365, the full list of IPv6 addresses that are supported by Office 365 can be found in the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span> <span data-ttu-id="98834-108">네트워크를 구성하고 적절한 IPv6 주소를 허용한 후 Microsoft 다운로드 센터에서 [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) 테스트 계획을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-108">After your network is configured and the appropriate IPv6 addresses are allowed, you can download the [Office 365 IPv6 test plan](https://go.microsoft.com/fwlink/?LinkId=293447) from the Microsoft Download Center.</span></span>
  
## <a name="ipv6-support-in-office-365-subscription-service"></a><span data-ttu-id="98834-109">Office 365 구독 서비스의 IPv6 지원</span><span class="sxs-lookup"><span data-stu-id="98834-109">IPv6 support in Office 365 subscription service</span></span>

### <a name="exchange-online-and-ipv6"></a><span data-ttu-id="98834-110">Exchange Online 및 IPv6</span><span class="sxs-lookup"><span data-stu-id="98834-110">Exchange Online and IPv6</span></span>

<span data-ttu-id="98834-111">Exchange Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 유선 네트워크와 무선 네트워크 모두에서 기본적으로 IPv6을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-111">If the program that you use to connect to Exchange Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="98834-112">Exchange Online에 대한 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="98834-112">If you want to control communications to Exchange Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="sharepoint-online-and-ipv6"></a><span data-ttu-id="98834-113">SharePoint Online 및 IPv6</span><span class="sxs-lookup"><span data-stu-id="98834-113">SharePoint Online and IPv6</span></span>

 <span data-ttu-id="98834-114">**Office 365 Government G1/G3/G4/K1** SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6을 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-114">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
 <span data-ttu-id="98834-115">**공용 다중 테넌트 클라우드** Microsoft는 요청 시 SharePoint Online IPv6을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-115">**Public multi-tenant cloud** Microsoft enables SharePoint Online IPv6 at your request.</span></span> <span data-ttu-id="98834-116">조직의 DNS 인프라에 대해 CIDR에서 고지된 IP 주소를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-116">You need to provide the CIDR notated IP addresses for your organization's DNS infrastructure.</span></span> <span data-ttu-id="98834-117">테넌트에 대해 IPv6을 사용하도록 설정하기 위해 다른 조직에서는 이 DNS 인프라를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-117">Keep in mind that this DNS infrastructure can't be shared by other organizations for IPv6 to be enabled for your tenant.</span></span> <span data-ttu-id="98834-118">IPv6을 사용하도록 설정한 후 SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98834-118">After IPv6 is enabled, if the program that you use to connect to SharePoint Online supports IPv6, it uses IPv6 by default.</span></span>
  
<span data-ttu-id="98834-119">SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 유선 네트워크와 무선 네트워크 모두에서 기본적으로 IPv6을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-119">If the program that you use to connect to SharePoint Online supports IPv6, it will use IPv6 by default on both wired and wireless networks.</span></span> <span data-ttu-id="98834-120">SharePoint Online에 대한 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="98834-120">If you want to control communications to SharePoint Online, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
 <span data-ttu-id="98834-121">**Office 365 Government G1/G3/G4/K1** SharePoint Online에 연결하는 데 사용하는 프로그램에서 IPv6을 지원하는 경우 기본적으로 IPv6을 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-121">**Office 365 Government G1/G3/G4/K1** If the program that you use to connect to SharePoint Online supports IPv6, it will attempt to use IPv6 by default.</span></span>
  
### <a name="skype-for-business-and-ipv6"></a><span data-ttu-id="98834-122">비즈니스용 Skype 및 IPv6</span><span class="sxs-lookup"><span data-stu-id="98834-122">Skype for Business and IPv6</span></span>

<span data-ttu-id="98834-123">IPv6은 비즈니스용 Skype에서 지원되지 않습니다. 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-123">Please be aware IPv6 is not supported in Skype for Business and can no longer be enabled.</span></span>

### <a name="microsoft-teams-and-ipv6"></a><span data-ttu-id="98834-124">Microsoft Teams 및 IPV6</span><span class="sxs-lookup"><span data-stu-id="98834-124">Microsoft Teams and IPV6</span></span>

<span data-ttu-id="98834-125">Microsoft Teams 직접 라우팅은 IPv4만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="98834-125">Microsoft Teams Direct Routing only supports IPv4.</span></span> <span data-ttu-id="98834-126">Microsoft Teams 서비스 및 클라이언트는 IPv4 및 IPv6을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-126">The Microsoft Teams service and client support both IPv4 and IPv6.</span></span> <span data-ttu-id="98834-127">Microsoft Teams와의 통신을 제어하려는 경우 [Office 365](urls-and-ip-address-ranges.md)URL 및 IP 주소 범위의 IP 주소 범위를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="98834-127">If you want to control communications to Microsoft Teams, use the IP address ranges in [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="exchange-online-protection-and-ipv6"></a><span data-ttu-id="98834-128">Exchange Online Protection 및 IPv6</span><span class="sxs-lookup"><span data-stu-id="98834-128">Exchange Online Protection and IPv6</span></span>

<span data-ttu-id="98834-129">전송 계층 보안 프로토콜을 통해 전송이 발생하는 경우 EOP(Exchange Online Protection)는 IPv6을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-129">Exchange Online Protection (EOP) supports IPv6 if the transmission occurs over Transport Layer Security Protocol.</span></span> <span data-ttu-id="98834-130">EOP 범위의 경우 [Office 365 URL 및 IP 주소 범위를 사용하세요.](urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="98834-130">For the EOP range, use [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md).</span></span>
  
### <a name="ipv6-support-for-office-365-government-offerings"></a><span data-ttu-id="98834-131">Office 365 정부 제품용 IPv6 지원</span><span class="sxs-lookup"><span data-stu-id="98834-131">IPv6 support for Office 365 government offerings</span></span>

<span data-ttu-id="98834-132">정부 제공에 대한 Office 365 IPv6 지원은 행정부 및 기관의 최고 정보 책임자에 대한 OMB(관리 및 예산국) 양해 및 IPv6(Federal Government의 IPv6) 도입에 대한 양해를 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-132">Office 365 IPv6 support for government offerings conforms to the Office of Management and Budget (OMB) Memorandum for Chief Information Officers of Executive Departments and Agencies, as well as the Federal Government Adoption of Internet Protocol Version 6 (IPv6) memorandum.</span></span> <span data-ttu-id="98834-133">[Microsoft Office 365 for Government는](https://go.microsoft.com/fwlink/p/?LinkId=325414) 미국 정부 데이터를 분계된 커뮤니티 클라우드에 저장하는 다중 테넌트 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="98834-133">[Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) is a multi-tenant service that stores US government data in a segregated community cloud.</span></span> <span data-ttu-id="98834-134">다른 Office 365 서비스와 마찬가지로 Exchange Online, 비즈니스용 Skype, SharePoint Online 및 엔터프라이즈용 Microsoft 365 앱을 비롯한 생산성 및 공동 작업 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-134">Like other Office 365 offerings, it provides productivity and collaboration services, including Exchange Online, Skype for Business, SharePoint Online, and Microsoft 365 Apps for enterprise.</span></span> 

<span data-ttu-id="98834-135">365 Microsoft Office 2013 이상에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98834-135">The Microsoft Office 365 government offerings apply only for 2013 and later.</span></span> <span data-ttu-id="98834-136">Office 365 정부 제공에 대한 자세한 내용은 [Government용 Office 365 발표: 미국 정부 커뮤니티 클라우드를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=325414)</span><span class="sxs-lookup"><span data-stu-id="98834-136">For more information about the Office 365 government offerings, see [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414).</span></span> <span data-ttu-id="98834-137">ITAR(International Traffic in Arms [Regulations)는 미국 USML(Munitions List)에서](https://go.microsoft.com/fwlink/p/?LinkId=325415)국방 관련 문서 및 서비스의 수출 및 가져오기 기능을 제어하는 미국 정부 규정 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="98834-137">International Traffic in Arms Regulations (ITAR) is a set of US government regulations that control the export and import of defense-related articles and services on the [United States Munitions List (USML)](https://go.microsoft.com/fwlink/p/?LinkId=325415).</span></span> 

<span data-ttu-id="98834-138">Microsoft Office 365 for Enterprise는 ITAR이 적용된 미국 연방 정보 보안 관리(FISMA) 인증 및 상업적 엔터티를 요구하는 미국 연방 기관에 대한 보안, 개인 정보 보호 및 규정 준수 요구 사항을 지원하는 Microsoft 생산성 솔루션에 대한 전용 호스팅 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-138">Microsoft Office 365 for Enterprises provides dedicated hosting services for Microsoft productivity solutions that support the security, privacy, and regulatory compliance requirements for US federal agencies requiring Federal Information Security Management (FISMA) certification and commercial entities subject to ITAR.</span></span>
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a><span data-ttu-id="98834-139">IPv6 및 Office 365를 사용할 때 고려해야 할 것</span><span class="sxs-lookup"><span data-stu-id="98834-139">Things to consider when using IPv6 and Office 365</span></span>

<span data-ttu-id="98834-140">IPv6을 사용하지 않도록 설정하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-140">We recommend that you do not disable IPv6.</span></span> <span data-ttu-id="98834-141">자세한 내용은 이 지침 문서를 [참조하세요.](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)</span><span class="sxs-lookup"><span data-stu-id="98834-141">For more information, see this [guidance article](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users).</span></span> <span data-ttu-id="98834-142">네트워크에서 사용되는 IP 버전을 확인하기 위해 다음을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="98834-142">To determine what IP versions are being used on your network, consider the following:</span></span>
  
- <span data-ttu-id="98834-143">명령 프롬프트에 **IPConfig** 명령이 표시될 때 "IPv6 주소" 또는 "임시 IPv6 주소"라는 행이 포함되어 있는 경우 환경에 IPv6이 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98834-143">If the display of the **IPConfig** command at the command prompt contains rows named "IPv6 Address" or "Temporary IPv6 Address," you have IPv6 in your environment.</span></span>

- <span data-ttu-id="98834-144">모든 IPv6 주소가 "fe80"으로 시작하고 "Link-Local IPv6 Address"라는 행에 해당하는 경우 환경에 IPv6이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98834-144">If all the IPv6 addresses begin with "fe80" and correspond to rows named "Link-Local IPv6 Address," you don't have IPv6 in your environment.</span></span>

<span data-ttu-id="98834-145">이러한 고려 사항이 네트워크에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-145">These considerations might apply to your network:</span></span>
  
- <span data-ttu-id="98834-146">공용 구독 서비스는 IPv6을 통해 신용 카드로 구매를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-146">The public subscription service does not support purchase by credit card over IPv6.</span></span> <span data-ttu-id="98834-147">이는 정부가 EA(정부 커뮤니티 클라우드) 라이선스를 기업계약 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-147">This does not apply to the Government Community Cloud (GCC) because governments have Enterprise Agreement (EA) licensing.</span></span>

- <span data-ttu-id="98834-148">IPv6에서는 일부 RMS(권한 관리 서비스) 시나리오를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-148">IPv6 does not support some Rights Management Services (RMS) scenarios.</span></span>

- <span data-ttu-id="98834-149">BlackBerry는 IPv6을 지원하지 ® Enterprise Server(BES)를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-149">IPv6 does not support BlackBerry® Enterprise Server (BES) because BlackBerry doesn't support IPv6.</span></span>

- <span data-ttu-id="98834-150">Office 365에서 AD FS(Active Directory Federation Services)를 사용하는 경우 IPv6을 사용하여 AD FS 네트워크 끝점을 Office 365에 광고하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98834-150">If you use Active Directory Federation Services (AD FS) with Office 365, advertising your AD FS network endpoint to Office 365 using IPv6 is not supported.</span></span> <span data-ttu-id="98834-151">Exchange Online을 사용할 때 AD FS DNS 항목에 AAAA 레코드를 포함하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98834-151">You should not include AAAA records in the AD FS DNS entry when using Exchange Online.</span></span> 

<span data-ttu-id="98834-152">다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/o365ip6]()</span><span class="sxs-lookup"><span data-stu-id="98834-152">Here's a short link you can use to come back: [https://aka.ms/o365ip6]()</span></span>
  
## <a name="see-also"></a><span data-ttu-id="98834-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98834-153">See also</span></span>

<span data-ttu-id="98834-154">[IPv6 학습 로드맵](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span><span class="sxs-lookup"><span data-stu-id="98834-154">[IPv6 Learning Roadmap](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))</span></span>
  
[<span data-ttu-id="98834-155">IPv6 사용 가이드</span><span class="sxs-lookup"><span data-stu-id="98834-155">IPv6 Survival Guide</span></span>](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)