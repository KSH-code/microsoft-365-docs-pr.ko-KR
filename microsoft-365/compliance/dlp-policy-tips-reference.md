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
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876827"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="8513f-103">데이터 손실 방지 정책 팁 참조</span><span class="sxs-lookup"><span data-stu-id="8513f-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="8513f-104">Outlook Web Access의 DLP 정책 팁은 다음을 제외한 DLP 정책의 Exchange 작업에 적용되는 모든 조건, 예외 및 작업에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="8513f-105">**조건:**</span><span class="sxs-lookup"><span data-stu-id="8513f-105">**Conditions:**</span></span>

- <span data-ttu-id="8513f-106">보낸 사람 Is</span><span class="sxs-lookup"><span data-stu-id="8513f-106">Sender Is</span></span>
- <span data-ttu-id="8513f-107">보낸 사람 도메인</span><span class="sxs-lookup"><span data-stu-id="8513f-107">Sender Domain Is</span></span>
- <span data-ttu-id="8513f-108">받는 사람이 다음의 구성원인 경우</span><span class="sxs-lookup"><span data-stu-id="8513f-108">Recipient is a member of</span></span>
- <span data-ttu-id="8513f-109">헤더에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-109">Header contains words or phrases</span></span>
- <span data-ttu-id="8513f-110">패턴 일치 헤더</span><span class="sxs-lookup"><span data-stu-id="8513f-110">Header matches patterns</span></span>
- <span data-ttu-id="8513f-111">문서 크기가 같거나 보다 크거나 같은 경우</span><span class="sxs-lookup"><span data-stu-id="8513f-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="8513f-112">메시지 유형은</span><span class="sxs-lookup"><span data-stu-id="8513f-112">Message type is</span></span>
- <span data-ttu-id="8513f-113">메시지 중요도</span><span class="sxs-lookup"><span data-stu-id="8513f-113">Message importance is</span></span>
- <span data-ttu-id="8513f-114">콘텐츠 문자 집합에 단어 포함</span><span class="sxs-lookup"><span data-stu-id="8513f-114">Content character set contains words</span></span>
- <span data-ttu-id="8513f-115">제목 또는 본문에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="8513f-116">제목 또는 본문이 패턴과 일치</span><span class="sxs-lookup"><span data-stu-id="8513f-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="8513f-117">콘텐츠 문자 집합에 단어 포함</span><span class="sxs-lookup"><span data-stu-id="8513f-117">Content character set contains words</span></span>
- <span data-ttu-id="8513f-118">콘텐츠 수신</span><span class="sxs-lookup"><span data-stu-id="8513f-118">Content is received from</span></span>
- <span data-ttu-id="8513f-119">보낸 사람이 정책 팁을 다시 정해 두었기</span><span class="sxs-lookup"><span data-stu-id="8513f-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="8513f-120">메시지 크기가 같거나 보다 크기</span><span class="sxs-lookup"><span data-stu-id="8513f-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="8513f-121">보낸 사람 AD 특성에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="8513f-122">보낸 사람 AD 특성이 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="8513f-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="8513f-123">문서 콘텐츠에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="8513f-124">문서 콘텐츠 일치 패턴</span><span class="sxs-lookup"><span data-stu-id="8513f-124">Document content matches patterns</span></span>

<span data-ttu-id="8513f-125">**작업:**</span><span class="sxs-lookup"><span data-stu-id="8513f-125">**Actions:**</span></span>

- <span data-ttu-id="8513f-126">승인을 위해 보낸 사람 관리자에게 메시지 전달</span><span class="sxs-lookup"><span data-stu-id="8513f-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="8513f-127">특정 승인자에 대한 승인을 위해 메시지 전달</span><span class="sxs-lookup"><span data-stu-id="8513f-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="8513f-128">메시지를 특정 사용자로 리디렉션</span><span class="sxs-lookup"><span data-stu-id="8513f-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="8513f-129">받는 사람 상자에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="8513f-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="8513f-130">Cc Box에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="8513f-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="8513f-131">Bcc Box에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="8513f-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="8513f-132">보낸 사람의 관리자를 받는 사람으로 추가</span><span class="sxs-lookup"><span data-stu-id="8513f-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="8513f-133">HTML 고지 조항 추가</span><span class="sxs-lookup"><span data-stu-id="8513f-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="8513f-134">전자 메일 제목 추가</span><span class="sxs-lookup"><span data-stu-id="8513f-134">Prepend email subject</span></span>
- <span data-ttu-id="8513f-135">O365 메시지 암호화 및 권한 보호 제거</span><span class="sxs-lookup"><span data-stu-id="8513f-135">Remove O365 Message Encryption and rights protection</span></span>
- <span data-ttu-id="8513f-136">제거</span><span class="sxs-lookup"><span data-stu-id="8513f-136">Remove</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="8513f-137">Outlook 2013 이상에서는 일부 조건 및 예외에 대한 정책 팁 표시 지원</span><span class="sxs-lookup"><span data-stu-id="8513f-137">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="8513f-138">현재 Outlook 2013 이상에서는 아래 언급된 조건 및 해당 예외와 별도로 조건이나 예외를 포함하지 않는 정책에 대한 정책 팁 표시를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-138">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="8513f-139">콘텐츠 포함(중요한 정보 유형에만 해당)</span><span class="sxs-lookup"><span data-stu-id="8513f-139">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="8513f-140">민감도 레이블이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-140">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="8513f-141">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="8513f-141">Content is shared</span></span>

<span data-ttu-id="8513f-142">모든 조건은 Outlook 클라이언트 앱에서 제작된 전자 메일에 대해 작동하며, 콘텐츠와 일치하고 콘텐츠에 보호 작업을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-142">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="8513f-143">그러나 사용자에게 정책 팁을 표시하는 것은 위에서 언급한 조건과는 별도로 사용되는 조건에 대해 아직 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-143">However, showing policy tips to users is not yet supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="8513f-144">Outlook 2013 이상에서는 일부 중요한 정보 유형에 대한 정책 팁 표시 지원</span><span class="sxs-lookup"><span data-stu-id="8513f-144">Outlook 2013 and later supports showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="8513f-145">데스크톱의 Outlook(2013 이상)에서 DLP 정책 팁을 표시하기 위해 검색될 예정인 바로 중요한 정보 유형 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-145">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) are the following :</span></span>

- <span data-ttu-id="8513f-146">ABA 라우팅 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-146">ABA Routing Number</span></span>
- <span data-ttu-id="8513f-147">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-147">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="8513f-148">호주 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-148">Australia Bank Account Number</span></span>
- <span data-ttu-id="8513f-149">호주 의료 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-149">Australia Medical Account Number</span></span>
- <span data-ttu-id="8513f-150">호주 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-150">Australia Passport Number</span></span>
- <span data-ttu-id="8513f-151">호주 세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-151">Australia Tax File Number</span></span>
- <span data-ttu-id="8513f-152">Azure DocumentDB Auth 키</span><span class="sxs-lookup"><span data-stu-id="8513f-152">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="8513f-153">Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-153">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="8513f-154">Azure IoT 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-154">Azure IoT Connection String</span></span>  
- <span data-ttu-id="8513f-155">Azure 게시 설정 암호</span><span class="sxs-lookup"><span data-stu-id="8513f-155">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="8513f-156">Azure Redis 캐시 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-156">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="8513f-157">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="8513f-157">Azure SAS</span></span>  
- <span data-ttu-id="8513f-158">Azure 서비스 버스 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-158">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="8513f-159">Azure Storage 계정 키</span><span class="sxs-lookup"><span data-stu-id="8513f-159">Azure Storage Account Key</span></span>  
- <span data-ttu-id="8513f-160">Azure Storage 계정 키(일반)</span><span class="sxs-lookup"><span data-stu-id="8513f-160">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="8513f-161">벨기에 국가 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-161">Belgium National Number</span></span>
- <span data-ttu-id="8513f-162">브라질 CPF 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-162">Brazil CPF Number</span></span>
- <span data-ttu-id="8513f-163">브라질 법인 번호(CNPJ)</span><span class="sxs-lookup"><span data-stu-id="8513f-163">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="8513f-164">	브라질 국가 ID 카드(RG)</span><span class="sxs-lookup"><span data-stu-id="8513f-164">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="8513f-165">캐나다 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-165">Canada Bank Account Number</span></span>
- <span data-ttu-id="8513f-166">캐나다 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-166">Canada Driver's License Number</span></span>
- <span data-ttu-id="8513f-167">캐나다 건강 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-167">Canada Health Service Number</span></span>
- <span data-ttu-id="8513f-168">캐나다 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-168">Canada Passport Number</span></span>
- <span data-ttu-id="8513f-169">캐나다 PHIN(개인 건강 식별 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-169">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="8513f-170">캐나다 사회 보험 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-170">Canada Social Insurance Number</span></span>
- <span data-ttu-id="8513f-171">	칠레 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-171">Chile Identity Card Number</span></span>
- <span data-ttu-id="8513f-172">	중국 주민 ID 카드(PRC) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-172">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="8513f-173">신용 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-173">Credit Card Number</span></span>
- <span data-ttu-id="8513f-174">크로아티아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-174">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="8513f-175">크로아티아 개인 식별(OIB) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-175">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="8513f-176">체코 개인 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-176">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="8513f-177">덴마크 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-177">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="8513f-178">DEA(약물 집행 기구) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-178">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="8513f-179">유럽 직불 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-179">EU Debit Card Number</span></span>
- <span data-ttu-id="8513f-180">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-180">EU Driver's License Number</span></span>  
- <span data-ttu-id="8513f-181">EU 국가 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-181">EU National Identification Number</span></span>  
- <span data-ttu-id="8513f-182">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-182">EU Passport Number</span></span>  
- <span data-ttu-id="8513f-183">EU SSN(사회 보장 번호) 또는 동등한 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-183">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="8513f-184">EU 세금 식별 번호(TIN)</span><span class="sxs-lookup"><span data-stu-id="8513f-184">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="8513f-185">핀란드 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-185">Finland National ID</span></span>
- <span data-ttu-id="8513f-186">핀란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-186">Finland Passport Number</span></span>
- <span data-ttu-id="8513f-187">프랑스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-187">France Driver's License Number</span></span>
- <span data-ttu-id="8513f-188">프랑스 국가 ID 카드(CNI)</span><span class="sxs-lookup"><span data-stu-id="8513f-188">France National ID Card (CNI)</span></span>
- <span data-ttu-id="8513f-189">프랑스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-189">France Passport Number</span></span>
- <span data-ttu-id="8513f-190">프랑스 사회 보장 번호(INSEE)</span><span class="sxs-lookup"><span data-stu-id="8513f-190">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="8513f-191">독일 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-191">German Driver's License Number</span></span>
- <span data-ttu-id="8513f-192">독일 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-192">German Passport Number</span></span>
- <span data-ttu-id="8513f-193">독일 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-193">Germany Identity Card Number</span></span>
- <span data-ttu-id="8513f-194">그리스 국가 ID 카드</span><span class="sxs-lookup"><span data-stu-id="8513f-194">Greece National ID Card</span></span>  
- <span data-ttu-id="8513f-195">HKID(홍콩 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-195">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="8513f-196">인도 PAN(영구 계정 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-196">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="8513f-197">인도 고유 ID(Aadhaar) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-197">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="8513f-198">인도네시아 ID 카드(KTP) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-198">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="8513f-199">IBAN(국제 은행 계좌 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-199">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="8513f-200">국제질병 분류(ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="8513f-200">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="8513f-201">국제질병 분류(ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="8513f-201">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="8513f-202">IP 주소</span><span class="sxs-lookup"><span data-stu-id="8513f-202">IP Address</span></span>
- <span data-ttu-id="8513f-203">아일랜드 PPS(개인 공공 서비스) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-203">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="8513f-204">이스라엘 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-204">Israel Bank Account Number</span></span>
- <span data-ttu-id="8513f-205">이스라엘 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-205">Israel National ID</span></span>
- <span data-ttu-id="8513f-206">이탈리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-206">Italy Driver's License Number</span></span>
- <span data-ttu-id="8513f-207">일본 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-207">Japan Bank Account Number</span></span>
- <span data-ttu-id="8513f-208">일본 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-208">Japan Driver's License Number</span></span>
- <span data-ttu-id="8513f-209">일본 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-209">Japan Passport Number</span></span>
- <span data-ttu-id="8513f-210">일본 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-210">Japan Resident Registration Number</span></span>
- <span data-ttu-id="8513f-211">일본 SIN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-211">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="8513f-212">일본어 거주 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-212">Japanese Residence Card Number</span></span>
- <span data-ttu-id="8513f-213">말레이시아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-213">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="8513f-214">네덜란드 시민 서비스(BSN) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-214">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="8513f-215">뉴질랜드 보건부 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-215">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="8513f-216">노르웨이 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-216">Norway Identity Number</span></span>  
- <span data-ttu-id="8513f-217">필리핀 통합 다목적 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-217">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="8513f-218">폴란드 ID 카드</span><span class="sxs-lookup"><span data-stu-id="8513f-218">Poland Identity Card</span></span>
- <span data-ttu-id="8513f-219">폴란드 국가 ID(PESEL)</span><span class="sxs-lookup"><span data-stu-id="8513f-219">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="8513f-220">폴란드 여권</span><span class="sxs-lookup"><span data-stu-id="8513f-220">Poland Passport</span></span>
- <span data-ttu-id="8513f-221">포르투갈 시민 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-221">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="8513f-222">사우디 아라비아 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-222">Saudi Arabia National ID</span></span>
- <span data-ttu-id="8513f-223">싱가포르 NRIC(국가 등록 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-223">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="8513f-224">남아프리카 공화국 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-224">South Africa Identification Number</span></span>  
- <span data-ttu-id="8513f-225">한국 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-225">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="8513f-226">스페인 SSN(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-226">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="8513f-227">SQL Server 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-227">SQL Server Connection String</span></span>  
- <span data-ttu-id="8513f-228">스웨덴 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-228">Sweden National ID</span></span>
- <span data-ttu-id="8513f-229">스웨덴 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-229">Sweden Passport Number</span></span>
- <span data-ttu-id="8513f-230">SWIFT 코드</span><span class="sxs-lookup"><span data-stu-id="8513f-230">SWIFT Code</span></span>
- <span data-ttu-id="8513f-231">대만 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-231">Taiwan National ID</span></span>
- <span data-ttu-id="8513f-232">	대만 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-232">Taiwan Passport Number</span></span>
- <span data-ttu-id="8513f-233">대만 거주 인증서(ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="8513f-233">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="8513f-234">태국어 인구 식별 코드</span><span class="sxs-lookup"><span data-stu-id="8513f-234">Thai Population Identification Code</span></span>
- <span data-ttu-id="8513f-235">터키어 국가 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-235">Turkish National Identification number</span></span>
- <span data-ttu-id="8513f-p103">영국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="8513f-p104">영국 선거 롤 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="8513f-p105">영국 국립 보건 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="8513f-p106">영국 NINO(국민 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="8513f-244">미국/영국</span><span class="sxs-lookup"><span data-stu-id="8513f-244">U.S. / U.K.</span></span> <span data-ttu-id="8513f-245">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8513f-245">Passport Number</span></span>
- <span data-ttu-id="8513f-246">미국 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-246">U.S. Bank Account Number</span></span>
- <span data-ttu-id="8513f-247">미국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-247">U.S. Driver's License Number</span></span>
- <span data-ttu-id="8513f-248">미국 ITIN(개인 납세자 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-248">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="8513f-249">미국 SSN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-249">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="8513f-250">사용자 지정 중요한 정보 유형은 위의 중요한 정보 유형 외에 DLP 정책 팁에도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-250">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="8513f-251">끝점의 데이터 손실 방지는 일부 중요한 정보 유형에 대한 정책 팁만 지원</span><span class="sxs-lookup"><span data-stu-id="8513f-251">Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="8513f-252">끝점 장치에 있는 문서에서 검색되는 바로 사용 가능한 중요한 정보 유형 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-252">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="8513f-253">ABA 라우팅 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-253">ABA Routing Number</span></span> 
- <span data-ttu-id="8513f-254">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-254">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="8513f-255">호주 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-255">Australia Bank Account Number</span></span> 
- <span data-ttu-id="8513f-256">호주 의료 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-256">Australia Medical Account Number</span></span> 
- <span data-ttu-id="8513f-257">호주 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-257">Australia Passport Number</span></span> 
- <span data-ttu-id="8513f-258">호주 세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-258">Australia Tax File Number</span></span> 
- <span data-ttu-id="8513f-259">오스트레일리아 비즈니스 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-259">Australian Business Number</span></span> 
- <span data-ttu-id="8513f-260">오스트레일리아 회사 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-260">Australian Company Number</span></span> 
- <span data-ttu-id="8513f-261">오스트리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-261">Austria Driver's License Number</span></span> 
- <span data-ttu-id="8513f-262">오스트리아 ID 카드</span><span class="sxs-lookup"><span data-stu-id="8513f-262">Austria Identity Card</span></span> 
- <span data-ttu-id="8513f-263">오스트리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-263">Austria Passport Number</span></span> 
- <span data-ttu-id="8513f-264">오스트리아 사회 보장 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-264">Austria Social Security Number</span></span> 
- <span data-ttu-id="8513f-265">오스트리아 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-265">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-266">오스트리아 부가가치세(VAT) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-266">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="8513f-267">Azure DocumentDB Auth 키</span><span class="sxs-lookup"><span data-stu-id="8513f-267">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="8513f-268">Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-268">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="8513f-269">Azure IoT 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-269">Azure IoT Connection String</span></span> 
- <span data-ttu-id="8513f-270">Azure 게시 설정 암호</span><span class="sxs-lookup"><span data-stu-id="8513f-270">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="8513f-271">Azure Redis 캐시 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-271">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="8513f-272">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="8513f-272">Azure SAS</span></span> 
- <span data-ttu-id="8513f-273">Azure 서비스 버스 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-273">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="8513f-274">Azure Storage 계정 키</span><span class="sxs-lookup"><span data-stu-id="8513f-274">Azure Storage Account Key</span></span> 
- <span data-ttu-id="8513f-275">Azure Storage 계정 키(일반)</span><span class="sxs-lookup"><span data-stu-id="8513f-275">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="8513f-276">벨기에 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-276">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="8513f-277">벨기에 국가 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-277">Belgium National Number</span></span> 
- <span data-ttu-id="8513f-278">벨기에 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-278">Belgium Passport Number</span></span> 
- <span data-ttu-id="8513f-279">벨기에 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-279">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="8513f-280">브라질 CPF 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-280">Brazil CPF Number</span></span> 
- <span data-ttu-id="8513f-281">브라질 법인 번호(CNPJ)</span><span class="sxs-lookup"><span data-stu-id="8513f-281">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="8513f-282">	브라질 국가 ID 카드(RG)</span><span class="sxs-lookup"><span data-stu-id="8513f-282">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="8513f-283">불가리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-283">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="8513f-284">불가리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-284">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="8513f-285">불가리아 제복민 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-285">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="8513f-286">캐나다 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-286">Canada Bank Account Number</span></span> 
- <span data-ttu-id="8513f-287">캐나다 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-287">Canada Driver's License Number</span></span> 
- <span data-ttu-id="8513f-288">캐나다 건강 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-288">Canada Health Service Number</span></span> 
- <span data-ttu-id="8513f-289">캐나다 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-289">Canada Passport Number</span></span> 
- <span data-ttu-id="8513f-290">캐나다 PHIN(개인 건강 식별 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-290">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="8513f-291">캐나다 사회 보험 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-291">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="8513f-292">	칠레 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-292">Chile Identity Card Number</span></span> 
- <span data-ttu-id="8513f-293">	중국 주민 ID 카드(PRC) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-293">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="8513f-294">신용 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-294">Credit Card Number</span></span> 
- <span data-ttu-id="8513f-295">크로아티아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-295">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="8513f-296">크로아티아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-296">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="8513f-297">크로아티아 국가 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-297">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="8513f-298">크로아티아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-298">Croatia Passport Number</span></span> 
- <span data-ttu-id="8513f-299">크로아티아 개인 식별(OIB) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-299">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="8513f-300">CSCAN-AZURE0060 Azure Storage 계정 공유 액세스 서명</span><span class="sxs-lookup"><span data-stu-id="8513f-300">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="8513f-301">CSCAN-GENERAL0140 일반 대칭 키</span><span class="sxs-lookup"><span data-stu-id="8513f-301">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="8513f-302">키프로스 드라이버의 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-302">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="8513f-303">키프로스 ID 카드</span><span class="sxs-lookup"><span data-stu-id="8513f-303">Cyprus Identity Card</span></span> 
- <span data-ttu-id="8513f-304">키프로스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-304">Cyprus Passport Number</span></span> 
- <span data-ttu-id="8513f-305">키프로스 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-305">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-306">체코 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-306">Czech Driver's License Number</span></span> 
- <span data-ttu-id="8513f-307">체코 개인 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-307">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="8513f-308">체코 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-308">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="8513f-309">덴마크 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-309">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="8513f-310">덴마크 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-310">Denmark Passport Number</span></span> 
- <span data-ttu-id="8513f-311">덴마크 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-311">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="8513f-312">DEA(약물 집행 기구) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-312">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="8513f-313">에스토니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-313">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="8513f-314">에스토니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-314">Estonia Passport Number</span></span> 
- <span data-ttu-id="8513f-315">에스토니아 개인 식별 코드</span><span class="sxs-lookup"><span data-stu-id="8513f-315">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="8513f-316">유럽 직불 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-316">EU Debit Card Number</span></span> 
- <span data-ttu-id="8513f-317">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-317">EU Driver's License Number</span></span> 
- <span data-ttu-id="8513f-318">EU 국가 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-318">EU National Identification Number</span></span> 
- <span data-ttu-id="8513f-319">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-319">EU Passport Number</span></span> 
- <span data-ttu-id="8513f-320">EU SSN(사회 보장 번호) 또는 동등한 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-320">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="8513f-321">EU 세금 식별 번호(TIN)</span><span class="sxs-lookup"><span data-stu-id="8513f-321">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="8513f-322">핀란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-322">Finland Driver's License Number</span></span> 
- <span data-ttu-id="8513f-323">핀란드 유럽 보건 보험 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-323">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="8513f-324">핀란드 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-324">Finland National ID</span></span> 
- <span data-ttu-id="8513f-325">핀란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-325">Finland Passport Number</span></span> 
- <span data-ttu-id="8513f-326">프랑스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-326">France Driver's License Number</span></span> 
- <span data-ttu-id="8513f-327">프랑스 건강 보험 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-327">France Health Insurance Number</span></span> 
- <span data-ttu-id="8513f-328">프랑스 국가 ID 카드(CNI)</span><span class="sxs-lookup"><span data-stu-id="8513f-328">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="8513f-329">프랑스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-329">France Passport Number</span></span> 
- <span data-ttu-id="8513f-330">프랑스 사회 보장 번호(INSEE)</span><span class="sxs-lookup"><span data-stu-id="8513f-330">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="8513f-331">프랑스 세금 식별 번호(numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="8513f-331">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="8513f-332">프랑스 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-332">France Value Added Tax Number</span></span> 
- <span data-ttu-id="8513f-333">독일 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-333">German Driver's License Number</span></span> 
- <span data-ttu-id="8513f-334">독일 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-334">German Passport Number</span></span> 
- <span data-ttu-id="8513f-335">독일 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-335">Germany Identity Card Number</span></span> 
- <span data-ttu-id="8513f-336">독일 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-336">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-337">독일 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-337">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="8513f-338">그리스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-338">Greece Driver's License Number</span></span> 
- <span data-ttu-id="8513f-339">그리스 국가 ID 카드</span><span class="sxs-lookup"><span data-stu-id="8513f-339">Greece National ID Card</span></span> 
- <span data-ttu-id="8513f-340">그리스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-340">Greece Passport Number</span></span> 
- <span data-ttu-id="8513f-341">그리스 AMKA(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-341">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="8513f-342">그리스어 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-342">Greek Tax identification Number</span></span> 
- <span data-ttu-id="8513f-343">HKID(홍콩 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-343">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="8513f-344">TAJ(헝가리어 사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-344">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="8513f-345">헝가리어 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-345">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="8513f-346">헝가리 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-346">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="8513f-347">헝가리 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-347">Hungary Passport Number</span></span> 
- <span data-ttu-id="8513f-348">헝가리 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-348">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="8513f-349">헝가리 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-349">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="8513f-350">인도 PAN(영구 계정 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-350">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="8513f-351">인도 고유 ID(Aadhaar) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-351">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="8513f-352">인도네시아 ID 카드(KTP) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-352">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="8513f-353">IBAN(국제 은행 계좌 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-353">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="8513f-354">국제질병 분류(ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="8513f-354">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="8513f-355">국제질병 분류(ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="8513f-355">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="8513f-356">IP 주소</span><span class="sxs-lookup"><span data-stu-id="8513f-356">IP Address</span></span> 
- <span data-ttu-id="8513f-357">아일랜드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-357">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="8513f-358">아일랜드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-358">Ireland Passport Number</span></span> 
- <span data-ttu-id="8513f-359">아일랜드 PPS(개인 공공 서비스) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-359">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="8513f-360">이스라엘 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-360">Israel Bank Account Number</span></span> 
- <span data-ttu-id="8513f-361">이스라엘 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-361">Israel National ID</span></span> 
- <span data-ttu-id="8513f-362">이탈리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-362">Italy Driver's License Number</span></span> 
- <span data-ttu-id="8513f-363">이탈리아 회계 코드</span><span class="sxs-lookup"><span data-stu-id="8513f-363">Italy Fiscal Code</span></span> 
- <span data-ttu-id="8513f-364">이탈리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-364">Italy Passport Number</span></span> 
- <span data-ttu-id="8513f-365">이탈리아 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-365">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="8513f-366">일본 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-366">Japan Bank Account Number</span></span> 
- <span data-ttu-id="8513f-367">일본 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-367">Japan Driver's License Number</span></span> 
- <span data-ttu-id="8513f-368">일본 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-368">Japan Passport Number</span></span> 
- <span data-ttu-id="8513f-369">일본 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-369">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="8513f-370">일본 SIN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-370">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="8513f-371">일본어 마이 번호 회사</span><span class="sxs-lookup"><span data-stu-id="8513f-371">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="8513f-372">일본어 마이 번호 개인</span><span class="sxs-lookup"><span data-stu-id="8513f-372">Japanese My Number Personal</span></span> 
- <span data-ttu-id="8513f-373">일본어 거주 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-373">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="8513f-374">라트비아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-374">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="8513f-375">라트비아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-375">Latvia Passport Number</span></span> 
- <span data-ttu-id="8513f-376">라트비아 개인 코드</span><span class="sxs-lookup"><span data-stu-id="8513f-376">Latvia Personal Code</span></span> 
- <span data-ttu-id="8513f-377">리투아니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-377">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="8513f-378">리투아니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-378">Lithuania Passport Number</span></span> 
- <span data-ttu-id="8513f-379">리투아니아 개인 코드</span><span class="sxs-lookup"><span data-stu-id="8513f-379">Lithuania Personal Code</span></span> 
- <span data-ttu-id="8513f-380">룩세르버그 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-380">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="8513f-381">룩룩부르크 국가 식별 번호(자연인)</span><span class="sxs-lookup"><span data-stu-id="8513f-381">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="8513f-382">룩세르버그 국가 식별 번호(자연인이 아닌 사람)</span><span class="sxs-lookup"><span data-stu-id="8513f-382">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="8513f-383">룩세르버그 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-383">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="8513f-384">말레이시아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-384">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="8513f-385">몰타 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-385">Malta Driver's License Number</span></span> 
- <span data-ttu-id="8513f-386">몰타 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-386">Malta Identity Card Number</span></span> 
- <span data-ttu-id="8513f-387">몰타 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-387">Malta Passport Number</span></span> 
- <span data-ttu-id="8513f-388">몰타 세금 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-388">Malta Tax ID Number</span></span> 
- <span data-ttu-id="8513f-389">네덜란드 시민 서비스(BSN) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-389">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="8513f-390">네덜란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-390">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="8513f-391">네덜란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-391">Netherlands Passport Number</span></span> 
- <span data-ttu-id="8513f-392">네덜란드 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-392">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-393">네덜란드 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-393">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="8513f-394">뉴질랜드 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-394">New Zealand bank account number</span></span> 
- <span data-ttu-id="8513f-395">뉴질랜드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-395">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="8513f-396">뉴질랜드 내륙 수익 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-396">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="8513f-397">뉴질랜드 보건부 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-397">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="8513f-398">뉴질랜드 사회 일지 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-398">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="8513f-399">노르웨이 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-399">Norway Identity Number</span></span> 
- <span data-ttu-id="8513f-400">필리핀 통합 다목적 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-400">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="8513f-401">폴란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-401">Poland Driver's License Number</span></span> 
- <span data-ttu-id="8513f-402">폴란드 ID 카드</span><span class="sxs-lookup"><span data-stu-id="8513f-402">Poland Identity Card</span></span> 
- <span data-ttu-id="8513f-403">폴란드 국가 ID(PESEL)</span><span class="sxs-lookup"><span data-stu-id="8513f-403">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="8513f-404">폴란드 여권</span><span class="sxs-lookup"><span data-stu-id="8513f-404">Poland Passport</span></span> 
- <span data-ttu-id="8513f-405">폴란드 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-405">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-406">폴란드어 REGON 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-406">Polish REGON Number</span></span> 
- <span data-ttu-id="8513f-407">포르투갈 시민 카드 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-407">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="8513f-408">포르투갈 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-408">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="8513f-409">포르투갈 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-409">Portugal Passport Number</span></span> 
- <span data-ttu-id="8513f-410">포르투갈 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-410">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-411">루마니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-411">Romania Driver's License Number</span></span> 
- <span data-ttu-id="8513f-412">루마니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-412">Romania Passport Number</span></span> 
- <span data-ttu-id="8513f-413">루마니아 CNP(개인 번호 코드)</span><span class="sxs-lookup"><span data-stu-id="8513f-413">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="8513f-414">러시아 여권 번호(국내)</span><span class="sxs-lookup"><span data-stu-id="8513f-414">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="8513f-415">러시아 여권 번호(국제)</span><span class="sxs-lookup"><span data-stu-id="8513f-415">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="8513f-416">사우디 아라비아 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-416">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="8513f-417">싱가포르 NRIC(국가 등록 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-417">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="8513f-418">슬로바키아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-418">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="8513f-419">슬로바키아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-419">Slovakia Passport Number</span></span> 
- <span data-ttu-id="8513f-420">슬로바키아 개인 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-420">Slovakia Personal Number</span></span> 
- <span data-ttu-id="8513f-421">Slovenia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="8513f-421">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="8513f-422">Slovenia Passport Number</span><span class="sxs-lookup"><span data-stu-id="8513f-422">Slovenia Passport Number</span></span> 
- <span data-ttu-id="8513f-423">솔로베니아 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-423">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-424">Slovenia Unique Master Citizen Number</span><span class="sxs-lookup"><span data-stu-id="8513f-424">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="8513f-425">남아프리카 공화국 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-425">South Africa Identification Number</span></span> 
- <span data-ttu-id="8513f-426">한국 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-426">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="8513f-427">스페인 DNI</span><span class="sxs-lookup"><span data-stu-id="8513f-427">Spain DNI</span></span> 
- <span data-ttu-id="8513f-428">스페인 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-428">Spain Driver's License Number</span></span> 
- <span data-ttu-id="8513f-429">스페인 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-429">Spain Passport Number</span></span> 
- <span data-ttu-id="8513f-430">스페인 SSN(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-430">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="8513f-431">스페인 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-431">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-432">SQL Server 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="8513f-432">SQL Server Connection String</span></span> 
- <span data-ttu-id="8513f-433">스웨덴 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-433">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="8513f-434">스웨덴 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-434">Sweden National ID</span></span> 
- <span data-ttu-id="8513f-435">스웨덴 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-435">Sweden Passport Number</span></span> 
- <span data-ttu-id="8513f-436">스웨덴 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-436">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="8513f-437">SWIFT 코드</span><span class="sxs-lookup"><span data-stu-id="8513f-437">SWIFT Code</span></span> 
- <span data-ttu-id="8513f-438">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="8513f-438">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="8513f-439">대만 국가 ID</span><span class="sxs-lookup"><span data-stu-id="8513f-439">Taiwan National ID</span></span> 
- <span data-ttu-id="8513f-440">	대만 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-440">Taiwan Passport Number</span></span> 
- <span data-ttu-id="8513f-441">대만 거주 인증서(ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="8513f-441">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="8513f-442">태국어 인구 식별 코드</span><span class="sxs-lookup"><span data-stu-id="8513f-442">Thai Population Identification Code</span></span> 
- <span data-ttu-id="8513f-443">터키어 국가 ID 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-443">Turkish National Identification number</span></span> 
- <span data-ttu-id="8513f-p108">영국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="8513f-p109">영국 선거 롤 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="8513f-p110">영국 국립 보건 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="8513f-p111">영국 NINO(국민 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="8513f-452">영국</span><span class="sxs-lookup"><span data-stu-id="8513f-452">U.K.</span></span> <span data-ttu-id="8513f-453">고유 납세자 참조 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-453">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="8513f-454">미국/영국</span><span class="sxs-lookup"><span data-stu-id="8513f-454">U.S. / U.K.</span></span> <span data-ttu-id="8513f-455">Passport Number</span><span class="sxs-lookup"><span data-stu-id="8513f-455">Passport Number</span></span> 
- <span data-ttu-id="8513f-456">미국 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-456">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="8513f-457">미국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="8513f-457">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="8513f-458">미국 ITIN(개인 납세자 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-458">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="8513f-459">미국 SSN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="8513f-459">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="8513f-460">우크라이나 여권 번호(국내)</span><span class="sxs-lookup"><span data-stu-id="8513f-460">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="8513f-461">우크라이나 여권 번호(국제)</span><span class="sxs-lookup"><span data-stu-id="8513f-461">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="8513f-462">사용자 지정 중요한 정보 유형은 위에 설명된 중요한 정보 유형 외에도 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-462">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="8513f-463">Microsoft 앱의 DLP 정책 팁 지원 매트릭스</span><span class="sxs-lookup"><span data-stu-id="8513f-463">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="8513f-464">**앱 및 플랫폼**</span><span class="sxs-lookup"><span data-stu-id="8513f-464">**App and platform**</span></span>|<span data-ttu-id="8513f-465">**DLP 정책 팁 지원**</span><span class="sxs-lookup"><span data-stu-id="8513f-465">**DLP policy tip support**</span></span>|<span data-ttu-id="8513f-466">**지원되는 중요한 정보 유형**</span><span class="sxs-lookup"><span data-stu-id="8513f-466">**Sensitive information types supported**</span></span>|<span data-ttu-id="8513f-467">**지원되는 사전 및 작업**</span><span class="sxs-lookup"><span data-stu-id="8513f-467">**Predicates and actions supported**</span></span>|<span data-ttu-id="8513f-468">**Comments**</span><span class="sxs-lookup"><span data-stu-id="8513f-468">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="8513f-469">**Outlook Web Access**</span><span class="sxs-lookup"><span data-stu-id="8513f-469">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8513f-470">모두</span><span class="sxs-lookup"><span data-stu-id="8513f-470">All</span></span>|<span data-ttu-id="8513f-471">하위 집합</span><span class="sxs-lookup"><span data-stu-id="8513f-471">Subset</span></span>|<span data-ttu-id="8513f-472">데이터 [손실 방지 정책 팁 참조 참조](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="8513f-472">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="8513f-473">**Outlook Win32(Outlook 2013 이상)**</span><span class="sxs-lookup"><span data-stu-id="8513f-473">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8513f-474">하위 집합</span><span class="sxs-lookup"><span data-stu-id="8513f-474">Subset</span></span>|<span data-ttu-id="8513f-475">하위 집합</span><span class="sxs-lookup"><span data-stu-id="8513f-475">Subset</span></span>|<span data-ttu-id="8513f-476">Outlook Win32에서 DLP 정책 팁을 표시하는 데 지원되는 중요한 정보 유형 및 DLP 조건에 대한 지원에 대한 자세한 내용은 Outlook [2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) 이상에서 일부 조건 및 예외에 대한 정책 팁 표시를 참조하고, [Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) 이상에서는 일부 중요한 정보 유형에 대한 정책 팁만 표시하는 것이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-476">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later supports showing policy tips for only some sensitive information types](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="8513f-477">**Outlook Mobile(iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="8513f-477">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8513f-478">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-478">None</span></span>|<span data-ttu-id="8513f-479">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-479">None</span></span>|<span data-ttu-id="8513f-480">DLP 정책 팁은 Outlook 모바일에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-480">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="8513f-481">**Sharepoint Online/비즈니스용 One Drive 웹 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8513f-481">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8513f-482">모두</span><span class="sxs-lookup"><span data-stu-id="8513f-482">All</span></span>|<span data-ttu-id="8513f-483">DLP의 모든 SPO/ODB 프레디트 및 작업</span><span class="sxs-lookup"><span data-stu-id="8513f-483">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="8513f-484">**Sharepoint Win32/ 비즈니스용 One Drive Win32 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8513f-484">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8513f-485">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-485">None</span></span>|<span data-ttu-id="8513f-486">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-486">None</span></span>|<span data-ttu-id="8513f-487">DLP 정책 팁은 Sharepoint 또는 OneDrive 데스크톱 클라이언트 앱에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-487">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="8513f-488">**Word, Excel, Powerpoint Web Client**</span><span class="sxs-lookup"><span data-stu-id="8513f-488">**Word, Excel, Powerpoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8513f-489">모두</span><span class="sxs-lookup"><span data-stu-id="8513f-489">All</span></span>|<span data-ttu-id="8513f-490">DLP의 모든 SPO/ODB 프레디트 및 작업</span><span class="sxs-lookup"><span data-stu-id="8513f-490">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="8513f-491">문서가 SPO 또는 ODB 웹앱에 호스트되어 있으며 DLP 정책이 이미 스탬프 처리된 경우 DLP 정책 팁이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-491">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="8513f-492">**Word, Excel, Powerpoint 모바일 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8513f-492">**Word, Excel, Powerpoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8513f-493">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-493">None</span></span>|<span data-ttu-id="8513f-494">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-494">None</span></span>|<span data-ttu-id="8513f-495">DLP 정책 팁은 Office용 모바일 앱에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-495">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="8513f-496">**Teams 웹/ Teams 데스크톱/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="8513f-496">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8513f-497">모두</span><span class="sxs-lookup"><span data-stu-id="8513f-497">All</span></span>|<span data-ttu-id="8513f-498">DLP 정책의 모든 Teams 예비자</span><span class="sxs-lookup"><span data-stu-id="8513f-498">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="8513f-499">정책 팁은 메시지가 "이 메시지에 플래그가 지정된 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-499">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="8513f-500">어떻게 해야 나요?"</span><span class="sxs-lookup"><span data-stu-id="8513f-500">What can I do?”</span></span> <span data-ttu-id="8513f-501">링크를 클릭할 때 사용자는 감지된 중요한 정보 유형을 검토하고 관리자가 허용하는 경우 문제를 재지정하거나 보고할 수 있습니다. 파일에 대한 정책 팁은 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-501">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="8513f-502">받는 사람이 문서에 액세스하는 경우 허용되지 않는 경우 액세스가 거부될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-502">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="8513f-503">**Win32 끝점 장치**</span><span class="sxs-lookup"><span data-stu-id="8513f-503">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="8513f-504">하위 집합</span><span class="sxs-lookup"><span data-stu-id="8513f-504">Subset</span></span>|<span data-ttu-id="8513f-505">DLP 정책의 모든 끝점 DLP 사문자 및 작업</span><span class="sxs-lookup"><span data-stu-id="8513f-505">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="8513f-506">일부 중요한 정보 유형에 대한 정책 팁 지원 끝점의 데이터 손실 [방지를 참조하세요.](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="8513f-506">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="8513f-507">**Mac 장치**</span><span class="sxs-lookup"><span data-stu-id="8513f-507">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8513f-508">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-508">None</span></span>|<span data-ttu-id="8513f-509">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-509">None</span></span>|<span data-ttu-id="8513f-510">현재 Mac 장치에서는 데이터 손실 방지를 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-510">Data loss prevention are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="8513f-511">**제3자 클라우드 앱**</span><span class="sxs-lookup"><span data-stu-id="8513f-511">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8513f-512">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-512">None</span></span>|<span data-ttu-id="8513f-513">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-513">None</span></span>|<span data-ttu-id="8513f-514">데이터 손실 방지</span><span class="sxs-lookup"><span data-stu-id="8513f-514">Data Loss Prevention</span></span>|
|<span data-ttu-id="8513f-515">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="8513f-515">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8513f-516">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-516">None</span></span>|<span data-ttu-id="8513f-517">없음</span><span class="sxs-lookup"><span data-stu-id="8513f-517">None</span></span>||
|<span data-ttu-id="8513f-518">**Word, Excel, Powerpoint Win32 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="8513f-518">**Word, Excel, Powerpoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="8513f-519">하위 집합</span><span class="sxs-lookup"><span data-stu-id="8513f-519">Subset</span></span>|<span data-ttu-id="8513f-520">하위 집합</span><span class="sxs-lookup"><span data-stu-id="8513f-520">Subset</span></span>|<span data-ttu-id="8513f-521">WXP 클라이언트 앱에 대한 정책 팁은 아래 또는 DLP 정책에 조건 또는 작업의 하위 집합이 있는 모든 DLP 정책에 대해 Sharepoint Online 또는 비즈니스용 One Drive 사이트에 저장된 문서에 대해 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="8513f-522">콘텐츠에 중요한 정보 유형 포함</span><span class="sxs-lookup"><span data-stu-id="8513f-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="8513f-523">액세스 범위(콘텐츠가 내부/외부적으로 공유)</span><span class="sxs-lookup"><span data-stu-id="8513f-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="8513f-524">사용자에게 알림(정책 팁/사용자 알림)</span><span class="sxs-lookup"><span data-stu-id="8513f-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="8513f-525">모든 사람 차단</span><span class="sxs-lookup"><span data-stu-id="8513f-525">Block everyone</span></span></li><li><span data-ttu-id="8513f-526">사고 보고서</span><span class="sxs-lookup"><span data-stu-id="8513f-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="8513f-527">다른 조건이나 작업이 있는 경우 해당 정책에 대한 DLP 정책 팁이 Word, Excel 또는 PowerPoint의 데스크톱 앱에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8513f-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span>|
||||||