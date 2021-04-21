---
title: 데이터 손실 방지 정책 팁 참조
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: DLP(데이터 손실 방지) 정책에 정책 팁을 추가하여 사용자에게 DLP 정책과 충돌하는 콘텐츠를 사용 중일 때 이를 알리는 방법을 알아보겠습니다.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 36e4d4f96146b51e0b31731c9e93222eed767045
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903805"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="99ce8-103">데이터 손실 방지 정책 팁 참조</span><span class="sxs-lookup"><span data-stu-id="99ce8-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="99ce8-104">Outlook Web Access의 DLP 정책 팁은 다음을 제외한 DLP 정책의 Exchange 작업에 적용되는 모든 조건, 예외 및 작업에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="99ce8-105">**조건:**</span><span class="sxs-lookup"><span data-stu-id="99ce8-105">**Conditions:**</span></span>

- <span data-ttu-id="99ce8-106">보낸 사람 Is</span><span class="sxs-lookup"><span data-stu-id="99ce8-106">Sender Is</span></span>
- <span data-ttu-id="99ce8-107">보낸 사람 도메인</span><span class="sxs-lookup"><span data-stu-id="99ce8-107">Sender Domain Is</span></span>
- <span data-ttu-id="99ce8-108">받는 사람이 다음의 구성원인 경우</span><span class="sxs-lookup"><span data-stu-id="99ce8-108">Recipient is a member of</span></span>
- <span data-ttu-id="99ce8-109">헤더에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-109">Header contains words or phrases</span></span>
- <span data-ttu-id="99ce8-110">패턴 일치 헤더</span><span class="sxs-lookup"><span data-stu-id="99ce8-110">Header matches patterns</span></span>
- <span data-ttu-id="99ce8-111">문서 크기가 같거나 보다 크거나 같은 경우</span><span class="sxs-lookup"><span data-stu-id="99ce8-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="99ce8-112">메시지 유형은</span><span class="sxs-lookup"><span data-stu-id="99ce8-112">Message type is</span></span>
- <span data-ttu-id="99ce8-113">메시지 중요도</span><span class="sxs-lookup"><span data-stu-id="99ce8-113">Message importance is</span></span>
- <span data-ttu-id="99ce8-114">콘텐츠 문자 집합에 단어 포함</span><span class="sxs-lookup"><span data-stu-id="99ce8-114">Content character set contains words</span></span>
- <span data-ttu-id="99ce8-115">제목 또는 본문에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="99ce8-116">제목 또는 본문이 패턴과 일치</span><span class="sxs-lookup"><span data-stu-id="99ce8-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="99ce8-117">콘텐츠 문자 집합에 단어 포함</span><span class="sxs-lookup"><span data-stu-id="99ce8-117">Content character set contains words</span></span>
- <span data-ttu-id="99ce8-118">콘텐츠 수신</span><span class="sxs-lookup"><span data-stu-id="99ce8-118">Content is received from</span></span>
- <span data-ttu-id="99ce8-119">보낸 사람이 정책 팁을 다시 정해 두었기</span><span class="sxs-lookup"><span data-stu-id="99ce8-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="99ce8-120">메시지 크기가 같거나 보다 크기</span><span class="sxs-lookup"><span data-stu-id="99ce8-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="99ce8-121">보낸 사람 AD 특성에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="99ce8-122">보낸 사람 AD 특성이 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="99ce8-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="99ce8-123">문서 콘텐츠에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="99ce8-124">문서 콘텐츠 일치 패턴</span><span class="sxs-lookup"><span data-stu-id="99ce8-124">Document content matches patterns</span></span>

<span data-ttu-id="99ce8-125">**작업:**</span><span class="sxs-lookup"><span data-stu-id="99ce8-125">**Actions:**</span></span>

- <span data-ttu-id="99ce8-126">승인을 위해 보낸 사람 관리자에게 메시지 전달</span><span class="sxs-lookup"><span data-stu-id="99ce8-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="99ce8-127">특정 승인자에 대한 승인을 위해 메시지 전달</span><span class="sxs-lookup"><span data-stu-id="99ce8-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="99ce8-128">메시지를 특정 사용자로 리디렉션</span><span class="sxs-lookup"><span data-stu-id="99ce8-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="99ce8-129">받는 사람 상자에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="99ce8-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="99ce8-130">Cc Box에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="99ce8-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="99ce8-131">Bcc Box에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="99ce8-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="99ce8-132">보낸 사람의 관리자를 받는 사람으로 추가</span><span class="sxs-lookup"><span data-stu-id="99ce8-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="99ce8-133">HTML 고지 조항 추가</span><span class="sxs-lookup"><span data-stu-id="99ce8-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="99ce8-134">전자 메일 제목 추가</span><span class="sxs-lookup"><span data-stu-id="99ce8-134">Prepend email subject</span></span>
- <span data-ttu-id="99ce8-135">O365 메시지 암호화 및 권한 보호 제거</span><span class="sxs-lookup"><span data-stu-id="99ce8-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="99ce8-136">Outlook 2013 이상에서는 일부 조건 및 예외에 대한 정책 팁 표시 지원</span><span class="sxs-lookup"><span data-stu-id="99ce8-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="99ce8-137">현재 Outlook 2013 이상에서는 아래 언급된 조건 및 해당 예외와 별도로 조건이나 예외를 포함하지 않는 정책에 대한 정책 팁 표시를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="99ce8-138">콘텐츠 포함(중요한 정보 유형에만 해당)</span><span class="sxs-lookup"><span data-stu-id="99ce8-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="99ce8-139">민감도 레이블이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="99ce8-140">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="99ce8-140">Content is shared</span></span>

<span data-ttu-id="99ce8-141">모든 조건은 Outlook 클라이언트 앱에서 제작된 전자 메일에 대해 작동하며, 콘텐츠와 일치하고 콘텐츠에 보호 작업을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="99ce8-142">그러나 사용자에게 정책 팁을 표시하는 것은 위에서 언급한 조건과는 별도로 사용되는 조건에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="99ce8-143">일부 중요한 정보 유형에 대한 정책 팁을 표시하는 데스크톱의 Outlook 2013 이상 및 Office 앱 지원</span><span class="sxs-lookup"><span data-stu-id="99ce8-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="99ce8-144">데스크톱의 Outlook(2013 이상) 및 데스크톱의 Office 앱(Word, Excel, PowerPoint)에서 DLP 정책 팁을 표시하기 위해 검색될 예정인 바로 중요한 정보 유형 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="99ce8-145">ABA 라우팅 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-145">ABA Routing Number</span></span>
- <span data-ttu-id="99ce8-146">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="99ce8-147">호주 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="99ce8-148">호주 의료 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="99ce8-149">호주 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-149">Australia Passport Number</span></span>
- <span data-ttu-id="99ce8-150">호주 세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-150">Australia Tax File Number</span></span>
- <span data-ttu-id="99ce8-151">Azure DocumentDB Auth 키</span><span class="sxs-lookup"><span data-stu-id="99ce8-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="99ce8-152">Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="99ce8-153">Azure IoT 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="99ce8-154">Azure 게시 설정 암호</span><span class="sxs-lookup"><span data-stu-id="99ce8-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="99ce8-155">Azure Redis 캐시 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="99ce8-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="99ce8-156">Azure SAS</span></span>  
- <span data-ttu-id="99ce8-157">Azure 서비스 버스 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="99ce8-158">Azure Storage 계정 키</span><span class="sxs-lookup"><span data-stu-id="99ce8-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="99ce8-159">Azure Storage 계정 키(일반)</span><span class="sxs-lookup"><span data-stu-id="99ce8-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="99ce8-160">벨기에 국가 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-160">Belgium National Number</span></span>
- <span data-ttu-id="99ce8-161">브라질 CPF 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-161">Brazil CPF Number</span></span>
- <span data-ttu-id="99ce8-162">브라질 법인 번호(CNPJ)</span><span class="sxs-lookup"><span data-stu-id="99ce8-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="99ce8-163">	브라질 국가 ID 카드(RG)</span><span class="sxs-lookup"><span data-stu-id="99ce8-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="99ce8-164">캐나다 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="99ce8-165">캐나다 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="99ce8-166">캐나다 건강 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-166">Canada Health Service Number</span></span>
- <span data-ttu-id="99ce8-167">캐나다 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-167">Canada Passport Number</span></span>
- <span data-ttu-id="99ce8-168">캐나다 PHIN(개인 건강 식별 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="99ce8-169">캐나다 사회 보험 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="99ce8-170">	칠레 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="99ce8-171">	중국 주민 ID 카드(PRC) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="99ce8-172">신용 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-172">Credit Card Number</span></span>
- <span data-ttu-id="99ce8-173">크로아티아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="99ce8-174">크로아티아 개인 식별(OIB) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="99ce8-175">체코 개인 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="99ce8-176">덴마크 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="99ce8-177">DEA(약물 집행 기구) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="99ce8-178">유럽 직불 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-178">EU Debit Card Number</span></span>
- <span data-ttu-id="99ce8-179">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="99ce8-180">EU 국가 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-180">EU National Identification Number</span></span>  
- <span data-ttu-id="99ce8-181">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-181">EU Passport Number</span></span>  
- <span data-ttu-id="99ce8-182">EU SSN(사회 보장 번호) 또는 동등한 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="99ce8-183">EU 세금 식별 번호(TIN)</span><span class="sxs-lookup"><span data-stu-id="99ce8-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="99ce8-184">핀란드 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-184">Finland National ID</span></span>
- <span data-ttu-id="99ce8-185">핀란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-185">Finland Passport Number</span></span>
- <span data-ttu-id="99ce8-186">프랑스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-186">France Driver's License Number</span></span>
- <span data-ttu-id="99ce8-187">프랑스 국가 ID 카드(CNI)</span><span class="sxs-lookup"><span data-stu-id="99ce8-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="99ce8-188">프랑스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-188">France Passport Number</span></span>
- <span data-ttu-id="99ce8-189">프랑스 사회 보장 번호(INSEE)</span><span class="sxs-lookup"><span data-stu-id="99ce8-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="99ce8-190">독일 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-190">German Driver's License Number</span></span>
- <span data-ttu-id="99ce8-191">독일 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-191">German Passport Number</span></span>
- <span data-ttu-id="99ce8-192">독일 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="99ce8-193">그리스 국가 ID 카드</span><span class="sxs-lookup"><span data-stu-id="99ce8-193">Greece National ID Card</span></span>  
- <span data-ttu-id="99ce8-194">HKID(홍콩 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="99ce8-195">인도 PAN(영구 계정 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="99ce8-196">인도 고유 ID(Aadhaar) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="99ce8-197">인도네시아 ID 카드(KTP) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="99ce8-198">IBAN(국제 은행 계좌 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="99ce8-199">국제질병 분류(ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="99ce8-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="99ce8-200">국제질병 분류(ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="99ce8-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="99ce8-201">IP 주소</span><span class="sxs-lookup"><span data-stu-id="99ce8-201">IP Address</span></span>
- <span data-ttu-id="99ce8-202">아일랜드 PPS(개인 공공 서비스) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="99ce8-203">이스라엘 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="99ce8-204">이스라엘 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-204">Israel National ID</span></span>
- <span data-ttu-id="99ce8-205">이탈리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="99ce8-206">일본 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="99ce8-207">일본 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="99ce8-208">일본 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-208">Japan Passport Number</span></span>
- <span data-ttu-id="99ce8-209">일본 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="99ce8-210">일본 SIN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="99ce8-211">일본어 거주 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="99ce8-212">말레이시아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="99ce8-213">네덜란드 시민 서비스(BSN) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="99ce8-214">뉴질랜드 보건부 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="99ce8-215">노르웨이 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-215">Norway Identity Number</span></span>  
- <span data-ttu-id="99ce8-216">필리핀 통합 다목적 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="99ce8-217">폴란드 ID 카드</span><span class="sxs-lookup"><span data-stu-id="99ce8-217">Poland Identity Card</span></span>
- <span data-ttu-id="99ce8-218">폴란드 국가 ID(PESEL)</span><span class="sxs-lookup"><span data-stu-id="99ce8-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="99ce8-219">폴란드 여권</span><span class="sxs-lookup"><span data-stu-id="99ce8-219">Poland Passport</span></span>
- <span data-ttu-id="99ce8-220">포르투갈 시민 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="99ce8-221">사우디 아라비아 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="99ce8-222">싱가포르 NRIC(국가 등록 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="99ce8-223">남아프리카 공화국 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="99ce8-224">한국 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="99ce8-225">스페인 SSN(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="99ce8-226">SQL Server 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="99ce8-227">스웨덴 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-227">Sweden National ID</span></span>
- <span data-ttu-id="99ce8-228">스웨덴 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-228">Sweden Passport Number</span></span>
- <span data-ttu-id="99ce8-229">SWIFT 코드</span><span class="sxs-lookup"><span data-stu-id="99ce8-229">SWIFT Code</span></span>
- <span data-ttu-id="99ce8-230">대만 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-230">Taiwan National ID</span></span>
- <span data-ttu-id="99ce8-231">	대만 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="99ce8-232">대만 거주 인증서(ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="99ce8-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="99ce8-233">태국어 인구 식별 코드</span><span class="sxs-lookup"><span data-stu-id="99ce8-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="99ce8-234">터키어 국가 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-234">Turkish National Identification number</span></span>
- <span data-ttu-id="99ce8-p103">영국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="99ce8-p104">영국 선거 롤 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="99ce8-p105">영국 국립 보건 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="99ce8-p106">영국 NINO(국민 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="99ce8-243">미국/영국</span><span class="sxs-lookup"><span data-stu-id="99ce8-243">U.S. / U.K.</span></span> <span data-ttu-id="99ce8-244">Passport Number</span><span class="sxs-lookup"><span data-stu-id="99ce8-244">Passport Number</span></span>
- <span data-ttu-id="99ce8-245">미국 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="99ce8-246">미국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="99ce8-247">미국 ITIN(개인 납세자 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="99ce8-248">미국 SSN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="99ce8-249">사용자 지정 중요한 정보 유형은 위의 중요한 정보 유형 외에 DLP 정책 팁에도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="99ce8-250">끝점 장치의 데이터 손실 방지는 일부 중요한 정보 유형에 대한 정책 팁만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="99ce8-251">끝점 장치에 있는 문서에서 검색되는 바로 사용 가능한 중요한 정보 유형 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="99ce8-252">ABA 라우팅 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-252">ABA Routing Number</span></span> 
- <span data-ttu-id="99ce8-253">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="99ce8-254">호주 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="99ce8-255">호주 의료 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="99ce8-256">호주 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-256">Australia Passport Number</span></span> 
- <span data-ttu-id="99ce8-257">호주 세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="99ce8-258">오스트레일리아 비즈니스 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-258">Australian Business Number</span></span> 
- <span data-ttu-id="99ce8-259">오스트레일리아 회사 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-259">Australian Company Number</span></span> 
- <span data-ttu-id="99ce8-260">오스트리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-261">오스트리아 ID 카드</span><span class="sxs-lookup"><span data-stu-id="99ce8-261">Austria Identity Card</span></span> 
- <span data-ttu-id="99ce8-262">오스트리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-262">Austria Passport Number</span></span> 
- <span data-ttu-id="99ce8-263">오스트리아 사회 보장 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="99ce8-264">오스트리아 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-265">오스트리아 부가가치세(VAT) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="99ce8-266">Azure DocumentDB Auth 키</span><span class="sxs-lookup"><span data-stu-id="99ce8-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="99ce8-267">Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="99ce8-268">Azure IoT 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="99ce8-269">Azure 게시 설정 암호</span><span class="sxs-lookup"><span data-stu-id="99ce8-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="99ce8-270">Azure Redis 캐시 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="99ce8-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="99ce8-271">Azure SAS</span></span> 
- <span data-ttu-id="99ce8-272">Azure 서비스 버스 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="99ce8-273">Azure Storage 계정 키</span><span class="sxs-lookup"><span data-stu-id="99ce8-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="99ce8-274">Azure Storage 계정 키(일반)</span><span class="sxs-lookup"><span data-stu-id="99ce8-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="99ce8-275">벨기에 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-276">벨기에 국가 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-276">Belgium National Number</span></span> 
- <span data-ttu-id="99ce8-277">벨기에 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="99ce8-278">벨기에 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="99ce8-279">브라질 CPF 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="99ce8-280">브라질 법인 번호(CNPJ)</span><span class="sxs-lookup"><span data-stu-id="99ce8-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="99ce8-281">	브라질 국가 ID 카드(RG)</span><span class="sxs-lookup"><span data-stu-id="99ce8-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="99ce8-282">불가리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-283">불가리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="99ce8-284">불가리아 제복민 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="99ce8-285">캐나다 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="99ce8-286">캐나다 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-287">캐나다 건강 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="99ce8-288">캐나다 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-288">Canada Passport Number</span></span> 
- <span data-ttu-id="99ce8-289">캐나다 PHIN(개인 건강 식별 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="99ce8-290">캐나다 사회 보험 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="99ce8-291">	칠레 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="99ce8-292">	중국 주민 ID 카드(PRC) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="99ce8-293">신용 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-293">Credit Card Number</span></span> 
- <span data-ttu-id="99ce8-294">크로아티아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-295">크로아티아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="99ce8-296">크로아티아 국가 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="99ce8-297">크로아티아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="99ce8-298">크로아티아 개인 식별(OIB) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="99ce8-299">CSCAN-AZURE0060 Azure Storage 계정 공유 액세스 서명</span><span class="sxs-lookup"><span data-stu-id="99ce8-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="99ce8-300">CSCAN-GENERAL0140 일반 대칭 키</span><span class="sxs-lookup"><span data-stu-id="99ce8-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="99ce8-301">키프로스 드라이버의 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-302">키프로스 ID 카드</span><span class="sxs-lookup"><span data-stu-id="99ce8-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="99ce8-303">키프로스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="99ce8-304">키프로스 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-305">체코 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-306">체코 개인 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="99ce8-307">체코 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="99ce8-308">덴마크 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-309">덴마크 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="99ce8-310">덴마크 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="99ce8-311">DEA(약물 집행 기구) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="99ce8-312">에스토니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-313">에스토니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="99ce8-314">에스토니아 개인 식별 코드</span><span class="sxs-lookup"><span data-stu-id="99ce8-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="99ce8-315">유럽 직불 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="99ce8-316">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-317">EU 국가 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-317">EU National Identification Number</span></span> 
- <span data-ttu-id="99ce8-318">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-318">EU Passport Number</span></span> 
- <span data-ttu-id="99ce8-319">EU SSN(사회 보장 번호) 또는 동등한 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="99ce8-320">EU 세금 식별 번호(TIN)</span><span class="sxs-lookup"><span data-stu-id="99ce8-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="99ce8-321">핀란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-322">핀란드 유럽 보건 보험 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="99ce8-323">핀란드 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-323">Finland National ID</span></span> 
- <span data-ttu-id="99ce8-324">핀란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-324">Finland Passport Number</span></span> 
- <span data-ttu-id="99ce8-325">프랑스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-325">France Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-326">프랑스 건강 보험 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="99ce8-327">프랑스 국가 ID 카드(CNI)</span><span class="sxs-lookup"><span data-stu-id="99ce8-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="99ce8-328">프랑스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-328">France Passport Number</span></span> 
- <span data-ttu-id="99ce8-329">프랑스 사회 보장 번호(INSEE)</span><span class="sxs-lookup"><span data-stu-id="99ce8-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="99ce8-330">프랑스 세금 식별 번호(numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="99ce8-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="99ce8-331">프랑스 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="99ce8-332">독일 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-332">German Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-333">독일 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-333">German Passport Number</span></span> 
- <span data-ttu-id="99ce8-334">독일 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="99ce8-335">독일 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-336">독일 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="99ce8-337">그리스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-338">그리스 국가 ID 카드</span><span class="sxs-lookup"><span data-stu-id="99ce8-338">Greece National ID Card</span></span> 
- <span data-ttu-id="99ce8-339">그리스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-339">Greece Passport Number</span></span> 
- <span data-ttu-id="99ce8-340">그리스 AMKA(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="99ce8-341">그리스어 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="99ce8-342">HKID(홍콩 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="99ce8-343">TAJ(헝가리어 사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="99ce8-344">헝가리어 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="99ce8-345">헝가리 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-346">헝가리 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="99ce8-347">헝가리 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="99ce8-348">헝가리 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="99ce8-349">인도 PAN(영구 계정 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="99ce8-350">인도 고유 ID(Aadhaar) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="99ce8-351">인도네시아 ID 카드(KTP) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="99ce8-352">IBAN(국제 은행 계좌 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="99ce8-353">국제질병 분류(ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="99ce8-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="99ce8-354">국제질병 분류(ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="99ce8-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="99ce8-355">IP 주소</span><span class="sxs-lookup"><span data-stu-id="99ce8-355">IP Address</span></span> 
- <span data-ttu-id="99ce8-356">아일랜드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-357">아일랜드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="99ce8-358">아일랜드 PPS(개인 공공 서비스) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="99ce8-359">이스라엘 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="99ce8-360">이스라엘 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-360">Israel National ID</span></span> 
- <span data-ttu-id="99ce8-361">이탈리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-362">이탈리아 회계 코드</span><span class="sxs-lookup"><span data-stu-id="99ce8-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="99ce8-363">이탈리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-363">Italy Passport Number</span></span> 
- <span data-ttu-id="99ce8-364">이탈리아 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="99ce8-365">일본 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="99ce8-366">일본 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-367">일본 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-367">Japan Passport Number</span></span> 
- <span data-ttu-id="99ce8-368">일본 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="99ce8-369">일본 SIN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="99ce8-370">일본어 마이 번호 회사</span><span class="sxs-lookup"><span data-stu-id="99ce8-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="99ce8-371">일본어 마이 번호 개인</span><span class="sxs-lookup"><span data-stu-id="99ce8-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="99ce8-372">일본어 거주 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="99ce8-373">라트비아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-374">라트비아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="99ce8-375">라트비아 개인 코드</span><span class="sxs-lookup"><span data-stu-id="99ce8-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="99ce8-376">리투아니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-377">리투아니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="99ce8-378">리투아니아 개인 코드</span><span class="sxs-lookup"><span data-stu-id="99ce8-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="99ce8-379">룩세르버그 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-380">룩룩부르크 국가 식별 번호(자연인)</span><span class="sxs-lookup"><span data-stu-id="99ce8-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="99ce8-381">룩세르버그 국가 식별 번호(자연인이 아닌 사람)</span><span class="sxs-lookup"><span data-stu-id="99ce8-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="99ce8-382">룩세르버그 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="99ce8-383">말레이시아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="99ce8-384">몰타 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-385">몰타 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="99ce8-386">몰타 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-386">Malta Passport Number</span></span> 
- <span data-ttu-id="99ce8-387">몰타 세금 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="99ce8-388">네덜란드 시민 서비스(BSN) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="99ce8-389">네덜란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-390">네덜란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="99ce8-391">네덜란드 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-392">네덜란드 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="99ce8-393">뉴질랜드 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="99ce8-394">뉴질랜드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="99ce8-395">뉴질랜드 내륙 수익 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="99ce8-396">뉴질랜드 보건부 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="99ce8-397">뉴질랜드 사회 일지 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="99ce8-398">노르웨이 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-398">Norway Identity Number</span></span> 
- <span data-ttu-id="99ce8-399">필리핀 통합 다목적 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="99ce8-400">폴란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-401">폴란드 ID 카드</span><span class="sxs-lookup"><span data-stu-id="99ce8-401">Poland Identity Card</span></span> 
- <span data-ttu-id="99ce8-402">폴란드 국가 ID(PESEL)</span><span class="sxs-lookup"><span data-stu-id="99ce8-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="99ce8-403">폴란드 여권</span><span class="sxs-lookup"><span data-stu-id="99ce8-403">Poland Passport</span></span> 
- <span data-ttu-id="99ce8-404">폴란드 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-405">폴란드어 REGON 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-405">Polish REGON Number</span></span> 
- <span data-ttu-id="99ce8-406">포르투갈 시민 카드 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="99ce8-407">포르투갈 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-408">포르투갈 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="99ce8-409">포르투갈 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-410">루마니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-411">루마니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-411">Romania Passport Number</span></span> 
- <span data-ttu-id="99ce8-412">루마니아 CNP(개인 번호 코드)</span><span class="sxs-lookup"><span data-stu-id="99ce8-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="99ce8-413">러시아 여권 번호(국내)</span><span class="sxs-lookup"><span data-stu-id="99ce8-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="99ce8-414">러시아 여권 번호(국제)</span><span class="sxs-lookup"><span data-stu-id="99ce8-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="99ce8-415">사우디 아라비아 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="99ce8-416">싱가포르 NRIC(국가 등록 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="99ce8-417">슬로바키아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-418">슬로바키아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="99ce8-419">슬로바키아 개인 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="99ce8-420">Slovenia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="99ce8-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-421">Slovenia Passport Number</span><span class="sxs-lookup"><span data-stu-id="99ce8-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="99ce8-422">솔로베니아 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-423">Slovenia Unique Master Citizen Number</span><span class="sxs-lookup"><span data-stu-id="99ce8-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="99ce8-424">남아프리카 공화국 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="99ce8-425">한국 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="99ce8-426">스페인 DNI</span><span class="sxs-lookup"><span data-stu-id="99ce8-426">Spain DNI</span></span> 
- <span data-ttu-id="99ce8-427">스페인 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-428">스페인 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-428">Spain Passport Number</span></span> 
- <span data-ttu-id="99ce8-429">스페인 SSN(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="99ce8-430">스페인 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-431">SQL Server 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="99ce8-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="99ce8-432">스웨덴 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-433">스웨덴 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-433">Sweden National ID</span></span> 
- <span data-ttu-id="99ce8-434">스웨덴 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="99ce8-435">스웨덴 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="99ce8-436">SWIFT 코드</span><span class="sxs-lookup"><span data-stu-id="99ce8-436">SWIFT Code</span></span> 
- <span data-ttu-id="99ce8-437">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="99ce8-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="99ce8-438">대만 국가 ID</span><span class="sxs-lookup"><span data-stu-id="99ce8-438">Taiwan National ID</span></span> 
- <span data-ttu-id="99ce8-439">	대만 여권 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="99ce8-440">대만 거주 인증서(ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="99ce8-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="99ce8-441">태국어 인구 식별 코드</span><span class="sxs-lookup"><span data-stu-id="99ce8-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="99ce8-442">터키어 국가 ID 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="99ce8-p108">영국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-p109">영국 선거 롤 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="99ce8-p110">영국 국립 보건 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="99ce8-p111">영국 NINO(국민 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="99ce8-451">영국</span><span class="sxs-lookup"><span data-stu-id="99ce8-451">U.K.</span></span> <span data-ttu-id="99ce8-452">고유 납세자 참조 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="99ce8-453">미국/영국</span><span class="sxs-lookup"><span data-stu-id="99ce8-453">U.S. / U.K.</span></span> <span data-ttu-id="99ce8-454">Passport Number</span><span class="sxs-lookup"><span data-stu-id="99ce8-454">Passport Number</span></span> 
- <span data-ttu-id="99ce8-455">미국 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="99ce8-456">미국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="99ce8-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="99ce8-457">미국 ITIN(개인 납세자 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="99ce8-458">미국 SSN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="99ce8-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="99ce8-459">우크라이나 여권 번호(국내)</span><span class="sxs-lookup"><span data-stu-id="99ce8-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="99ce8-460">우크라이나 여권 번호(국제)</span><span class="sxs-lookup"><span data-stu-id="99ce8-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="99ce8-461">사용자 지정 중요한 정보 유형은 위에 설명된 중요한 정보 유형 외에도 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="99ce8-462">Microsoft 앱의 DLP 정책 팁 지원 매트릭스</span><span class="sxs-lookup"><span data-stu-id="99ce8-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="99ce8-463">**앱 및 플랫폼**</span><span class="sxs-lookup"><span data-stu-id="99ce8-463">**App and platform**</span></span>|<span data-ttu-id="99ce8-464">**DLP 정책 팁 지원**</span><span class="sxs-lookup"><span data-stu-id="99ce8-464">**DLP policy tip support**</span></span>|<span data-ttu-id="99ce8-465">**지원되는 중요한 정보 유형**</span><span class="sxs-lookup"><span data-stu-id="99ce8-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="99ce8-466">**지원되는 사전 및 작업**</span><span class="sxs-lookup"><span data-stu-id="99ce8-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="99ce8-467">**Comments**</span><span class="sxs-lookup"><span data-stu-id="99ce8-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="99ce8-468">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="99ce8-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="99ce8-469">모두</span><span class="sxs-lookup"><span data-stu-id="99ce8-469">All</span></span>|<span data-ttu-id="99ce8-470">하위 집합</span><span class="sxs-lookup"><span data-stu-id="99ce8-470">Subset</span></span>|<span data-ttu-id="99ce8-471">데이터 [손실 방지 정책 팁 참조 참조](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="99ce8-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="99ce8-472">**Outlook Win32(Outlook 2013 이상)**</span><span class="sxs-lookup"><span data-stu-id="99ce8-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="99ce8-473">하위 집합</span><span class="sxs-lookup"><span data-stu-id="99ce8-473">Subset</span></span>|<span data-ttu-id="99ce8-474">하위 집합</span><span class="sxs-lookup"><span data-stu-id="99ce8-474">Subset</span></span>|<span data-ttu-id="99ce8-475">[Outlook Win32에서](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) DLP 정책 팁을 표시하는 데 지원되는 작업 및 중요한 정보 유형 및 DLP 조건에 대한 지원에 대한 자세한 내용은 일부 중요한 정보 유형에 대한 정책 팁만 표시하는 데스크톱의 Office 앱 지원 및 [일부](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) 조건 및 예외에 대한 정책 팁 표시를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ce8-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="99ce8-476">**Outlook Mobile(iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="99ce8-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="99ce8-477">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-477">None</span></span>|<span data-ttu-id="99ce8-478">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-478">None</span></span>|<span data-ttu-id="99ce8-479">DLP 정책 팁은 Outlook 모바일에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="99ce8-480">**Sharepoint Online/비즈니스용 One Drive 웹 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="99ce8-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="99ce8-481">모두</span><span class="sxs-lookup"><span data-stu-id="99ce8-481">All</span></span>|<span data-ttu-id="99ce8-482">DLP의 모든 SPO/ODB 프레디트 및 작업</span><span class="sxs-lookup"><span data-stu-id="99ce8-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="99ce8-483">**Sharepoint Win32/ 비즈니스용 One Drive Win32 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="99ce8-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="99ce8-484">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-484">None</span></span>|<span data-ttu-id="99ce8-485">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-485">None</span></span>|<span data-ttu-id="99ce8-486">DLP 정책 팁은 Sharepoint 또는 OneDrive 데스크톱 클라이언트 앱에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="99ce8-487">**Word, Excel, PowerPoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="99ce8-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="99ce8-488">모두</span><span class="sxs-lookup"><span data-stu-id="99ce8-488">All</span></span>|<span data-ttu-id="99ce8-489">DLP의 모든 SPO/ODB 프레디트 및 작업</span><span class="sxs-lookup"><span data-stu-id="99ce8-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="99ce8-490">문서가 SPO 또는 ODB 웹앱에 호스트되어 있으며 DLP 정책이 이미 스탬프 처리된 경우 DLP 정책 팁이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="99ce8-491">**Word, Excel, PowerPoint 모바일 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="99ce8-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="99ce8-492">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-492">None</span></span>|<span data-ttu-id="99ce8-493">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-493">None</span></span>|<span data-ttu-id="99ce8-494">DLP 정책 팁은 Office용 모바일 앱에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="99ce8-495">**Teams 웹/ Teams 데스크톱/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="99ce8-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="99ce8-496">모두</span><span class="sxs-lookup"><span data-stu-id="99ce8-496">All</span></span>|<span data-ttu-id="99ce8-497">DLP 정책의 모든 Teams 예비자</span><span class="sxs-lookup"><span data-stu-id="99ce8-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="99ce8-498">정책 팁은 메시지가 "이 메시지에 플래그가 지정된 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="99ce8-499">어떻게 해야 나요?"</span><span class="sxs-lookup"><span data-stu-id="99ce8-499">What can I do?”</span></span> <span data-ttu-id="99ce8-500">링크를 클릭할 때 사용자는 감지된 중요한 정보 유형을 검토하고 관리자가 허용하는 경우 문제를 재지정하거나 보고할 수 있습니다. 파일에 대한 정책 팁은 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="99ce8-501">받는 사람이 문서에 액세스하는 경우 허용되지 않는 경우 액세스가 거부될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="99ce8-502">**Win32 끝점 장치**</span><span class="sxs-lookup"><span data-stu-id="99ce8-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="99ce8-503">하위 집합</span><span class="sxs-lookup"><span data-stu-id="99ce8-503">Subset</span></span>|<span data-ttu-id="99ce8-504">DLP 정책의 모든 끝점 DLP 사문자 및 작업</span><span class="sxs-lookup"><span data-stu-id="99ce8-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="99ce8-505">일부 중요한 정보 유형에 대한 정책 팁 지원 끝점의 데이터 손실 [방지를 참조하세요.](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="99ce8-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="99ce8-506">**Mac 장치**</span><span class="sxs-lookup"><span data-stu-id="99ce8-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="99ce8-507">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-507">None</span></span>|<span data-ttu-id="99ce8-508">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-508">None</span></span>|<span data-ttu-id="99ce8-509">데이터 손실 방지 정책은 현재 Mac 장치에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="99ce8-510">**제3자 클라우드 앱**</span><span class="sxs-lookup"><span data-stu-id="99ce8-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="99ce8-511">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-511">None</span></span>|<span data-ttu-id="99ce8-512">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-512">None</span></span>|<span data-ttu-id="99ce8-513">데이터 손실 방지 정책 팁은 제3자 클라우드 앱에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="99ce8-514">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="99ce8-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="99ce8-515">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-515">None</span></span>|<span data-ttu-id="99ce8-516">없음</span><span class="sxs-lookup"><span data-stu-id="99ce8-516">None</span></span>||
|<span data-ttu-id="99ce8-517">**Word, Excel, PowerPoint Win32 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="99ce8-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="99ce8-518">하위 집합</span><span class="sxs-lookup"><span data-stu-id="99ce8-518">Subset</span></span>|<span data-ttu-id="99ce8-519">하위 집합</span><span class="sxs-lookup"><span data-stu-id="99ce8-519">Subset</span></span>|<span data-ttu-id="99ce8-520">지원되는 중요한 정보 유형 목록에 대한 일부 중요한 정보 유형에 대한 정책 팁만 보여주는 데스크톱의 [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) 이상 및 Office 앱을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ce8-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="99ce8-521">WXP 클라이언트 앱에 대한 정책 팁은 아래 또는 DLP 정책에 조건 또는 작업의 하위 집합이 있는 모든 DLP 정책에 대해 Sharepoint Online 또는 비즈니스용 One Drive 사이트에 저장된 문서에 대해 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="99ce8-522">콘텐츠에 중요한 정보 유형 포함</span><span class="sxs-lookup"><span data-stu-id="99ce8-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="99ce8-523">액세스 범위(콘텐츠가 내부/외부적으로 공유)</span><span class="sxs-lookup"><span data-stu-id="99ce8-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="99ce8-524">사용자에게 알림(정책 팁/사용자 알림)</span><span class="sxs-lookup"><span data-stu-id="99ce8-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="99ce8-525">모든 사람 차단</span><span class="sxs-lookup"><span data-stu-id="99ce8-525">Block everyone</span></span></li><li><span data-ttu-id="99ce8-526">사고 보고서</span><span class="sxs-lookup"><span data-stu-id="99ce8-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="99ce8-527">다른 조건이나 작업이 있는 경우 해당 정책에 대한 DLP 정책 팁이 Word, Excel 또는 PowerPoint의 데스크톱 앱에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99ce8-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="99ce8-528">자세한 [내용은 Excel, PowerPoint 및 Word의](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) 정책 팁을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99ce8-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
