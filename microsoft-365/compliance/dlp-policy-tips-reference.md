---
title: 데이터 손실 방지 정책 팁 참조
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: DLP(데이터 손실 방지) 정책에 정책 팁을 추가하여 사용자에게 DLP 정책과 충돌하는 콘텐츠를 사용 중일 때 이를 알리는 방법을 알아보겠습니다.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 0c42569da3fcac40d3121a59f7dc004f25dd3f74
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086762"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="d4781-103">데이터 손실 방지 정책 팁 참조</span><span class="sxs-lookup"><span data-stu-id="d4781-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="d4781-104">Outlook Web Access의 DLP 정책 팁은 다음을 제외한 DLP 정책의 Exchange 작업에 적용되는 모든 조건, 예외 및 작업에 대해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="d4781-105">**조건:**</span><span class="sxs-lookup"><span data-stu-id="d4781-105">**Conditions:**</span></span>

- <span data-ttu-id="d4781-106">보낸 사람 Is</span><span class="sxs-lookup"><span data-stu-id="d4781-106">Sender Is</span></span>
- <span data-ttu-id="d4781-107">보낸 사람 도메인</span><span class="sxs-lookup"><span data-stu-id="d4781-107">Sender Domain Is</span></span>
- <span data-ttu-id="d4781-108">받는 사람이 다음의 구성원인 경우</span><span class="sxs-lookup"><span data-stu-id="d4781-108">Recipient is a member of</span></span>
- <span data-ttu-id="d4781-109">헤더에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-109">Header contains words or phrases</span></span>
- <span data-ttu-id="d4781-110">패턴 일치 헤더</span><span class="sxs-lookup"><span data-stu-id="d4781-110">Header matches patterns</span></span>
- <span data-ttu-id="d4781-111">문서 크기가 같거나 보다 크거나 같은 경우</span><span class="sxs-lookup"><span data-stu-id="d4781-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="d4781-112">메시지 유형은</span><span class="sxs-lookup"><span data-stu-id="d4781-112">Message type is</span></span>
- <span data-ttu-id="d4781-113">메시지 중요도</span><span class="sxs-lookup"><span data-stu-id="d4781-113">Message importance is</span></span>
- <span data-ttu-id="d4781-114">콘텐츠 문자 집합에 단어 포함</span><span class="sxs-lookup"><span data-stu-id="d4781-114">Content character set contains words</span></span>
- <span data-ttu-id="d4781-115">제목 또는 본문에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="d4781-116">제목 또는 본문이 패턴과 일치</span><span class="sxs-lookup"><span data-stu-id="d4781-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="d4781-117">콘텐츠 문자 집합에 단어 포함</span><span class="sxs-lookup"><span data-stu-id="d4781-117">Content character set contains words</span></span>
- <span data-ttu-id="d4781-118">콘텐츠 수신</span><span class="sxs-lookup"><span data-stu-id="d4781-118">Content is received from</span></span>
- <span data-ttu-id="d4781-119">보낸 사람이 정책 팁을 다시 정해 두었기</span><span class="sxs-lookup"><span data-stu-id="d4781-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="d4781-120">메시지 크기가 같거나 보다 크기</span><span class="sxs-lookup"><span data-stu-id="d4781-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="d4781-121">보낸 사람 AD 특성에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="d4781-122">보낸 사람 AD 특성이 패턴 일치</span><span class="sxs-lookup"><span data-stu-id="d4781-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="d4781-123">문서 콘텐츠에 단어 또는 구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="d4781-124">문서 콘텐츠 일치 패턴</span><span class="sxs-lookup"><span data-stu-id="d4781-124">Document content matches patterns</span></span>

<span data-ttu-id="d4781-125">**작업:**</span><span class="sxs-lookup"><span data-stu-id="d4781-125">**Actions:**</span></span>

- <span data-ttu-id="d4781-126">승인을 위해 보낸 사람 관리자에게 메시지 전달</span><span class="sxs-lookup"><span data-stu-id="d4781-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="d4781-127">특정 승인자에 대한 승인을 위해 메시지 전달</span><span class="sxs-lookup"><span data-stu-id="d4781-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="d4781-128">메시지를 특정 사용자로 리디렉션</span><span class="sxs-lookup"><span data-stu-id="d4781-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="d4781-129">받는 사람 상자에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="d4781-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="d4781-130">Cc Box에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="d4781-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="d4781-131">Bcc Box에 받는 사람 추가</span><span class="sxs-lookup"><span data-stu-id="d4781-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="d4781-132">보낸 사람의 관리자를 받는 사람으로 추가</span><span class="sxs-lookup"><span data-stu-id="d4781-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="d4781-133">HTML 고지 조항 추가</span><span class="sxs-lookup"><span data-stu-id="d4781-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="d4781-134">전자 메일 제목 추가</span><span class="sxs-lookup"><span data-stu-id="d4781-134">Prepend email subject</span></span>
- <span data-ttu-id="d4781-135">O365 메시지 암호화 및 권한 보호 제거</span><span class="sxs-lookup"><span data-stu-id="d4781-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="d4781-136">Outlook 2013 이상에서는 일부 조건 및 예외에 대한 정책 팁 표시 지원</span><span class="sxs-lookup"><span data-stu-id="d4781-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="d4781-137">현재 Outlook 2013 이상에서는 아래 언급된 조건 및 해당 예외와 별도로 조건이나 예외를 포함하지 않는 정책에 대한 정책 팁 표시를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="d4781-138">콘텐츠 포함(중요한 정보 유형에만 해당)</span><span class="sxs-lookup"><span data-stu-id="d4781-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="d4781-139">민감도 레이블이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="d4781-140">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="d4781-140">Content is shared</span></span>

<span data-ttu-id="d4781-141">모든 조건은 Outlook 클라이언트 앱에서 작성된 전자 메일에 대해 작동하며, 콘텐츠와 일치하고 콘텐츠에 보호 작업을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="d4781-142">그러나 사용자에게 정책 팁을 표시하는 것은 위에서 언급한 조건과는 별도로 사용되는 조건에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="d4781-143">Outlook 2013 이상 및 Office 데스크톱의 앱 지원에는 일부 중요한 정보 유형에 대한 정책 팁만 표시</span><span class="sxs-lookup"><span data-stu-id="d4781-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="d4781-144">데스크톱의 Outlook(2013 이상) 및 데스크톱의 Office 앱(Word, Excel, PowerPoint)에 DLP 정책 팁을 표시하기 위해 검색될 예정인 바로 중요한 정보 유형 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="d4781-145">ABA 라우팅 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-145">ABA Routing Number</span></span>
- <span data-ttu-id="d4781-146">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="d4781-147">호주 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="d4781-148">호주 의료 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="d4781-149">호주 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-149">Australia Passport Number</span></span>
- <span data-ttu-id="d4781-150">호주 세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-150">Australia Tax File Number</span></span>
- <span data-ttu-id="d4781-151">Azure DocumentDB Auth 키</span><span class="sxs-lookup"><span data-stu-id="d4781-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="d4781-152">Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="d4781-153">Azure IoT 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="d4781-154">Azure 게시 설정 암호</span><span class="sxs-lookup"><span data-stu-id="d4781-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="d4781-155">Azure Redis 캐시 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="d4781-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="d4781-156">Azure SAS</span></span>  
- <span data-ttu-id="d4781-157">Azure Service Bus 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="d4781-158">Azure Storage 계정 키</span><span class="sxs-lookup"><span data-stu-id="d4781-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="d4781-159">Azure Storage 계정 키(일반)</span><span class="sxs-lookup"><span data-stu-id="d4781-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="d4781-160">벨기에 국가 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-160">Belgium National Number</span></span>
- <span data-ttu-id="d4781-161">브라질 CPF 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-161">Brazil CPF Number</span></span>
- <span data-ttu-id="d4781-162">브라질 법인 번호(CNPJ)</span><span class="sxs-lookup"><span data-stu-id="d4781-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="d4781-163">	브라질 국가 ID 카드(RG)</span><span class="sxs-lookup"><span data-stu-id="d4781-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="d4781-164">캐나다 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="d4781-165">캐나다 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="d4781-166">캐나다 건강 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-166">Canada Health Service Number</span></span>
- <span data-ttu-id="d4781-167">캐나다 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-167">Canada Passport Number</span></span>
- <span data-ttu-id="d4781-168">캐나다 PHIN(개인 건강 식별 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="d4781-169">캐나다 사회 보험 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="d4781-170">	칠레 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="d4781-171">	중국 주민 ID 카드(PRC) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="d4781-172">신용 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-172">Credit Card Number</span></span>
- <span data-ttu-id="d4781-173">크로아티아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="d4781-174">크로아티아 개인 식별(OIB) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="d4781-175">체코 개인 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="d4781-176">덴마크 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="d4781-177">DEA(약물 집행 기구) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="d4781-178">유럽 직불 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-178">EU Debit Card Number</span></span>
- <span data-ttu-id="d4781-179">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="d4781-180">EU 국가 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-180">EU National Identification Number</span></span>  
- <span data-ttu-id="d4781-181">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-181">EU Passport Number</span></span>  
- <span data-ttu-id="d4781-182">EU SSN(사회 보장 번호) 또는 동등한 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="d4781-183">EU 세금 식별 번호(TIN)</span><span class="sxs-lookup"><span data-stu-id="d4781-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="d4781-184">핀란드 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-184">Finland National ID</span></span>
- <span data-ttu-id="d4781-185">핀란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-185">Finland Passport Number</span></span>
- <span data-ttu-id="d4781-186">프랑스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-186">France Driver's License Number</span></span>
- <span data-ttu-id="d4781-187">프랑스 국가 ID 카드(CNI)</span><span class="sxs-lookup"><span data-stu-id="d4781-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="d4781-188">프랑스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-188">France Passport Number</span></span>
- <span data-ttu-id="d4781-189">프랑스 사회 보장 번호(INSEE)</span><span class="sxs-lookup"><span data-stu-id="d4781-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="d4781-190">독일 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-190">German Driver's License Number</span></span>
- <span data-ttu-id="d4781-191">독일 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-191">German Passport Number</span></span>
- <span data-ttu-id="d4781-192">독일 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="d4781-193">그리스 국가 ID 카드</span><span class="sxs-lookup"><span data-stu-id="d4781-193">Greece National ID Card</span></span>  
- <span data-ttu-id="d4781-194">HKID(홍콩 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="d4781-195">인도 PAN(영구 계정 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="d4781-196">인도 고유 ID(Aadhaar) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="d4781-197">인도네시아 ID 카드(KTP) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="d4781-198">IBAN(국제 은행 계좌 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="d4781-199">국제질병 분류(ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="d4781-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="d4781-200">국제질병 분류(ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="d4781-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="d4781-201">IP 주소</span><span class="sxs-lookup"><span data-stu-id="d4781-201">IP Address</span></span>
- <span data-ttu-id="d4781-202">아일랜드 PPS(개인 공공 서비스) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="d4781-203">이스라엘 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="d4781-204">이스라엘 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-204">Israel National ID</span></span>
- <span data-ttu-id="d4781-205">이탈리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="d4781-206">일본 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="d4781-207">일본 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="d4781-208">일본 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-208">Japan Passport Number</span></span>
- <span data-ttu-id="d4781-209">일본 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="d4781-210">일본 SIN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="d4781-211">일본어 거주 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="d4781-212">말레이시아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="d4781-213">네덜란드 시민 서비스(BSN) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="d4781-214">뉴질랜드 보건부 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="d4781-215">노르웨이 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-215">Norway Identity Number</span></span>  
- <span data-ttu-id="d4781-216">필리핀 통합 다목적 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="d4781-217">폴란드 ID 카드</span><span class="sxs-lookup"><span data-stu-id="d4781-217">Poland Identity Card</span></span>
- <span data-ttu-id="d4781-218">폴란드 국가 ID(PESEL)</span><span class="sxs-lookup"><span data-stu-id="d4781-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="d4781-219">폴란드 여권</span><span class="sxs-lookup"><span data-stu-id="d4781-219">Poland Passport</span></span>
- <span data-ttu-id="d4781-220">포르투갈 시민 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="d4781-221">사우디 아라비아 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="d4781-222">싱가포르 NRIC(국가 등록 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="d4781-223">남아프리카 공화국 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="d4781-224">한국 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="d4781-225">스페인 SSN(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="d4781-226">SQL Server 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="d4781-227">스웨덴 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-227">Sweden National ID</span></span>
- <span data-ttu-id="d4781-228">스웨덴 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-228">Sweden Passport Number</span></span>
- <span data-ttu-id="d4781-229">SWIFT 코드</span><span class="sxs-lookup"><span data-stu-id="d4781-229">SWIFT Code</span></span>
- <span data-ttu-id="d4781-230">대만 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-230">Taiwan National ID</span></span>
- <span data-ttu-id="d4781-231">	대만 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="d4781-232">대만 거주 인증서(ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="d4781-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="d4781-233">태국어 인구 식별 코드</span><span class="sxs-lookup"><span data-stu-id="d4781-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="d4781-234">터키어 국가 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-234">Turkish National Identification number</span></span>
- <span data-ttu-id="d4781-p103">영국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="d4781-p104">영국 선거 롤 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="d4781-p105">영국 국립 보건 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="d4781-p106">영국 NINO(국민 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="d4781-p107">미국/영국 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-p107">U.S. / U.K. Passport Number</span></span>
- <span data-ttu-id="d4781-245">미국 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="d4781-246">미국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="d4781-247">미국 ITIN(개인 납세자 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="d4781-248">미국 SSN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="d4781-249">사용자 지정 중요한 정보 유형은 위의 중요한 정보 유형 외에 DLP 정책 팁에도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="d4781-250">끝점 장치의 데이터 손실 방지는 일부 중요한 정보 유형에 대한 정책 팁만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="d4781-251">끝점 장치에 있는 문서에서 검색되는 바로 사용 가능한 중요한 정보 유형 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="d4781-252">ABA 라우팅 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-252">ABA Routing Number</span></span> 
- <span data-ttu-id="d4781-253">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="d4781-254">호주 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="d4781-255">호주 의료 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="d4781-256">호주 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-256">Australia Passport Number</span></span> 
- <span data-ttu-id="d4781-257">호주 세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="d4781-258">오스트레일리아 비즈니스 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-258">Australian Business Number</span></span> 
- <span data-ttu-id="d4781-259">오스트레일리아 회사 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-259">Australian Company Number</span></span> 
- <span data-ttu-id="d4781-260">오스트리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="d4781-261">오스트리아 ID 카드</span><span class="sxs-lookup"><span data-stu-id="d4781-261">Austria Identity Card</span></span> 
- <span data-ttu-id="d4781-262">오스트리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-262">Austria Passport Number</span></span> 
- <span data-ttu-id="d4781-263">오스트리아 사회 보장 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="d4781-264">오스트리아 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-265">오스트리아 부가가치세(VAT) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="d4781-266">Azure DocumentDB Auth 키</span><span class="sxs-lookup"><span data-stu-id="d4781-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="d4781-267">Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="d4781-268">Azure IoT 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="d4781-269">Azure 게시 설정 암호</span><span class="sxs-lookup"><span data-stu-id="d4781-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="d4781-270">Azure Redis 캐시 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="d4781-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="d4781-271">Azure SAS</span></span> 
- <span data-ttu-id="d4781-272">Azure Service Bus 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="d4781-273">Azure Storage 계정 키</span><span class="sxs-lookup"><span data-stu-id="d4781-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="d4781-274">Azure Storage 계정 키(일반)</span><span class="sxs-lookup"><span data-stu-id="d4781-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="d4781-275">벨기에 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="d4781-276">벨기에 국가 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-276">Belgium National Number</span></span> 
- <span data-ttu-id="d4781-277">벨기에 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="d4781-278">벨기에 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="d4781-279">브라질 CPF 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="d4781-280">브라질 법인 번호(CNPJ)</span><span class="sxs-lookup"><span data-stu-id="d4781-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="d4781-281">	브라질 국가 ID 카드(RG)</span><span class="sxs-lookup"><span data-stu-id="d4781-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="d4781-282">불가리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="d4781-283">불가리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="d4781-284">불가리아 제복민 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="d4781-285">캐나다 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="d4781-286">캐나다 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="d4781-287">캐나다 건강 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="d4781-288">캐나다 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-288">Canada Passport Number</span></span> 
- <span data-ttu-id="d4781-289">캐나다 PHIN(개인 건강 식별 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="d4781-290">캐나다 사회 보험 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="d4781-291">	칠레 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="d4781-292">	중국 주민 ID 카드(PRC) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="d4781-293">신용 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-293">Credit Card Number</span></span> 
- <span data-ttu-id="d4781-294">크로아티아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="d4781-295">크로아티아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="d4781-296">크로아티아 국가 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="d4781-297">크로아티아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="d4781-298">크로아티아 개인 식별(OIB) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="d4781-299">CSCAN-AZURE0060 Azure Storage 계정 공유 액세스 서명</span><span class="sxs-lookup"><span data-stu-id="d4781-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="d4781-300">CSCAN-GENERAL0140 일반 대칭 키</span><span class="sxs-lookup"><span data-stu-id="d4781-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="d4781-301">키프로스 드라이버의 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="d4781-302">키프로스 ID 카드</span><span class="sxs-lookup"><span data-stu-id="d4781-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="d4781-303">키프로스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="d4781-304">키프로스 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-305">체코 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="d4781-306">체코 개인 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="d4781-307">체코 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="d4781-308">덴마크 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="d4781-309">덴마크 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="d4781-310">덴마크 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="d4781-311">DEA(약물 집행 기구) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="d4781-312">에스토니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="d4781-313">에스토니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="d4781-314">에스토니아 개인 식별 코드</span><span class="sxs-lookup"><span data-stu-id="d4781-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="d4781-315">유럽 직불 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="d4781-316">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="d4781-317">EU 국가 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-317">EU National Identification Number</span></span> 
- <span data-ttu-id="d4781-318">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-318">EU Passport Number</span></span> 
- <span data-ttu-id="d4781-319">EU SSN(사회 보장 번호) 또는 동등한 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="d4781-320">EU 세금 식별 번호(TIN)</span><span class="sxs-lookup"><span data-stu-id="d4781-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="d4781-321">핀란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="d4781-322">핀란드 유럽 보건 보험 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="d4781-323">핀란드 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-323">Finland National ID</span></span> 
- <span data-ttu-id="d4781-324">핀란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-324">Finland Passport Number</span></span> 
- <span data-ttu-id="d4781-325">프랑스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-325">France Driver's License Number</span></span> 
- <span data-ttu-id="d4781-326">프랑스 건강 보험 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="d4781-327">프랑스 국가 ID 카드(CNI)</span><span class="sxs-lookup"><span data-stu-id="d4781-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="d4781-328">프랑스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-328">France Passport Number</span></span> 
- <span data-ttu-id="d4781-329">프랑스 사회 보장 번호(INSEE)</span><span class="sxs-lookup"><span data-stu-id="d4781-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="d4781-330">프랑스 세금 식별 번호(numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="d4781-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="d4781-331">프랑스 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="d4781-332">독일 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-332">German Driver's License Number</span></span> 
- <span data-ttu-id="d4781-333">독일 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-333">German Passport Number</span></span> 
- <span data-ttu-id="d4781-334">독일 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="d4781-335">독일 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-336">독일 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="d4781-337">그리스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="d4781-338">그리스 국가 ID 카드</span><span class="sxs-lookup"><span data-stu-id="d4781-338">Greece National ID Card</span></span> 
- <span data-ttu-id="d4781-339">그리스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-339">Greece Passport Number</span></span> 
- <span data-ttu-id="d4781-340">그리스 AMKA(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="d4781-341">그리스어 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="d4781-342">HKID(홍콩 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="d4781-343">TAJ(헝가리어 사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="d4781-344">헝가리어 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="d4781-345">헝가리 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="d4781-346">헝가리 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="d4781-347">헝가리 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="d4781-348">헝가리 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="d4781-349">인도 PAN(영구 계정 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="d4781-350">인도 고유 ID(Aadhaar) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="d4781-351">인도네시아 ID 카드(KTP) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="d4781-352">IBAN(국제 은행 계좌 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="d4781-353">국제질병 분류(ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="d4781-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="d4781-354">국제질병 분류(ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="d4781-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="d4781-355">IP 주소</span><span class="sxs-lookup"><span data-stu-id="d4781-355">IP Address</span></span> 
- <span data-ttu-id="d4781-356">아일랜드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="d4781-357">아일랜드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="d4781-358">아일랜드 PPS(개인 공공 서비스) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="d4781-359">이스라엘 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="d4781-360">이스라엘 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-360">Israel National ID</span></span> 
- <span data-ttu-id="d4781-361">이탈리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="d4781-362">이탈리아 회계 코드</span><span class="sxs-lookup"><span data-stu-id="d4781-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="d4781-363">이탈리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-363">Italy Passport Number</span></span> 
- <span data-ttu-id="d4781-364">이탈리아 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="d4781-365">일본 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="d4781-366">일본 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="d4781-367">일본 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-367">Japan Passport Number</span></span> 
- <span data-ttu-id="d4781-368">일본 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="d4781-369">일본 SIN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="d4781-370">일본어 마이 번호 회사</span><span class="sxs-lookup"><span data-stu-id="d4781-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="d4781-371">일본어 마이 번호 개인</span><span class="sxs-lookup"><span data-stu-id="d4781-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="d4781-372">일본어 거주 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="d4781-373">라트비아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="d4781-374">라트비아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="d4781-375">라트비아 개인 코드</span><span class="sxs-lookup"><span data-stu-id="d4781-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="d4781-376">리투아니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="d4781-377">리투아니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="d4781-378">리투아니아 개인 코드</span><span class="sxs-lookup"><span data-stu-id="d4781-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="d4781-379">룩세르버그 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="d4781-380">룩룩부르크 국가 식별 번호(자연인)</span><span class="sxs-lookup"><span data-stu-id="d4781-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="d4781-381">룩세르버그 국가 식별 번호(자연인이 아닌 사람)</span><span class="sxs-lookup"><span data-stu-id="d4781-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="d4781-382">룩세르버그 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="d4781-383">말레이시아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="d4781-384">몰타 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="d4781-385">몰타 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="d4781-386">몰타 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-386">Malta Passport Number</span></span> 
- <span data-ttu-id="d4781-387">몰타 세금 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="d4781-388">네덜란드 시민 서비스(BSN) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="d4781-389">네덜란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="d4781-390">네덜란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="d4781-391">네덜란드 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-392">네덜란드 부가가치세 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="d4781-393">뉴질랜드 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="d4781-394">뉴질랜드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="d4781-395">뉴질랜드 내륙 수익 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="d4781-396">뉴질랜드 보건부 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="d4781-397">뉴질랜드 사회 일지 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="d4781-398">노르웨이 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-398">Norway Identity Number</span></span> 
- <span data-ttu-id="d4781-399">필리핀 통합 다목적 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="d4781-400">폴란드 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="d4781-401">폴란드 ID 카드</span><span class="sxs-lookup"><span data-stu-id="d4781-401">Poland Identity Card</span></span> 
- <span data-ttu-id="d4781-402">폴란드 국가 ID(PESEL)</span><span class="sxs-lookup"><span data-stu-id="d4781-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="d4781-403">폴란드 여권</span><span class="sxs-lookup"><span data-stu-id="d4781-403">Poland Passport</span></span> 
- <span data-ttu-id="d4781-404">폴란드 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-405">폴란드어 REGON 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-405">Polish REGON Number</span></span> 
- <span data-ttu-id="d4781-406">포르투갈 시민 카드 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="d4781-407">포르투갈 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="d4781-408">포르투갈 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="d4781-409">포르투갈 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-410">루마니아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="d4781-411">루마니아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-411">Romania Passport Number</span></span> 
- <span data-ttu-id="d4781-412">루마니아 CNP(개인 번호 코드)</span><span class="sxs-lookup"><span data-stu-id="d4781-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="d4781-413">러시아 여권 번호(국내)</span><span class="sxs-lookup"><span data-stu-id="d4781-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="d4781-414">러시아 여권 번호(국제)</span><span class="sxs-lookup"><span data-stu-id="d4781-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="d4781-415">사우디 아라비아 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="d4781-416">싱가포르 NRIC(국가 등록 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="d4781-417">슬로바키아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="d4781-418">슬로바키아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="d4781-419">슬로바키아 개인 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="d4781-420">Slovenia Driver's License Number</span><span class="sxs-lookup"><span data-stu-id="d4781-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="d4781-421">Slovenia Passport Number</span><span class="sxs-lookup"><span data-stu-id="d4781-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="d4781-422">솔로베니아 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-423">Slovenia Unique Master Citizen Number</span><span class="sxs-lookup"><span data-stu-id="d4781-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="d4781-424">남아프리카 공화국 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="d4781-425">한국 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="d4781-426">스페인 DNI</span><span class="sxs-lookup"><span data-stu-id="d4781-426">Spain DNI</span></span> 
- <span data-ttu-id="d4781-427">스페인 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="d4781-428">스페인 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-428">Spain Passport Number</span></span> 
- <span data-ttu-id="d4781-429">스페인 SSN(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="d4781-430">스페인 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-431">SQL Server 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="d4781-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="d4781-432">스웨덴 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="d4781-433">스웨덴 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-433">Sweden National ID</span></span> 
- <span data-ttu-id="d4781-434">스웨덴 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="d4781-435">스웨덴 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="d4781-436">SWIFT 코드</span><span class="sxs-lookup"><span data-stu-id="d4781-436">SWIFT Code</span></span> 
- <span data-ttu-id="d4781-437">Swiss Social Security Number AHV</span><span class="sxs-lookup"><span data-stu-id="d4781-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="d4781-438">대만 국가 ID</span><span class="sxs-lookup"><span data-stu-id="d4781-438">Taiwan National ID</span></span> 
- <span data-ttu-id="d4781-439">	대만 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="d4781-440">대만 거주 인증서(ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="d4781-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="d4781-441">태국어 인구 식별 코드</span><span class="sxs-lookup"><span data-stu-id="d4781-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="d4781-442">터키어 국가 ID 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="d4781-p108">영국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="d4781-p109">영국 선거 롤 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="d4781-p110">영국 국립 보건 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="d4781-p111">영국 NINO(국민 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="d4781-451">영국</span><span class="sxs-lookup"><span data-stu-id="d4781-451">U.K.</span></span> <span data-ttu-id="d4781-452">고유 납세자 참조 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="d4781-p113">미국/영국 여권 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-p113">U.S. / U.K. Passport Number</span></span> 
- <span data-ttu-id="d4781-455">미국 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="d4781-456">미국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="d4781-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="d4781-457">미국 ITIN(개인 납세자 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="d4781-458">미국 SSN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="d4781-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="d4781-459">우크라이나 여권 번호(국내)</span><span class="sxs-lookup"><span data-stu-id="d4781-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="d4781-460">우크라이나 여권 번호(국제)</span><span class="sxs-lookup"><span data-stu-id="d4781-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="d4781-461">사용자 지정 중요한 정보 유형은 위에 설명된 중요한 정보 유형 외에도 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="d4781-462">Microsoft 앱의 DLP 정책 팁 지원 매트릭스</span><span class="sxs-lookup"><span data-stu-id="d4781-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="d4781-463">**앱 및 플랫폼**</span><span class="sxs-lookup"><span data-stu-id="d4781-463">**App and platform**</span></span>|<span data-ttu-id="d4781-464">**DLP 정책 팁 지원**</span><span class="sxs-lookup"><span data-stu-id="d4781-464">**DLP policy tip support**</span></span>|<span data-ttu-id="d4781-465">**지원되는 중요한 정보 유형**</span><span class="sxs-lookup"><span data-stu-id="d4781-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="d4781-466">**지원되는 사전 및 작업**</span><span class="sxs-lookup"><span data-stu-id="d4781-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="d4781-467">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d4781-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="d4781-468">**Outlook 웹 액세스**</span><span class="sxs-lookup"><span data-stu-id="d4781-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="d4781-469">모두</span><span class="sxs-lookup"><span data-stu-id="d4781-469">All</span></span>|<span data-ttu-id="d4781-470">하위 집합</span><span class="sxs-lookup"><span data-stu-id="d4781-470">Subset</span></span>|<span data-ttu-id="d4781-471">데이터 [손실 방지 정책 팁 참조 참조](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="d4781-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="d4781-472">**Outlook Win32(Outlook 2013 이상)**</span><span class="sxs-lookup"><span data-stu-id="d4781-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="d4781-473">하위 집합</span><span class="sxs-lookup"><span data-stu-id="d4781-473">Subset</span></span>|<span data-ttu-id="d4781-474">하위 집합</span><span class="sxs-lookup"><span data-stu-id="d4781-474">Subset</span></span>|<span data-ttu-id="d4781-475">Outlook [2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) 이상에서는 일부 조건 및 예외에 대한 정책 팁만 표시하고 [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) 이상 및 데스크톱의 Office 앱 지원에서는 중요한 정보 유형 및 DLP 조건에 대한 지원에 대한 자세한 내용과 Outlook Win32에 대한 DLP 정책 팁을 표시하는 데 지원되는 작업에 대한 정책 팁만 보여 주실 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="d4781-476">**Outlook 모바일(iOS, Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="d4781-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="d4781-477">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-477">None</span></span>|<span data-ttu-id="d4781-478">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-478">None</span></span>|<span data-ttu-id="d4781-479">DLP 정책 팁은 모바일에서 Outlook 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="d4781-480">**Sharepoint Online/비즈니스용 One Drive 웹 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="d4781-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="d4781-481">모두</span><span class="sxs-lookup"><span data-stu-id="d4781-481">All</span></span>|<span data-ttu-id="d4781-482">DLP의 모든 SPO/ODB 프레디트 및 작업</span><span class="sxs-lookup"><span data-stu-id="d4781-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="d4781-483">**Sharepoint Win32/ 비즈니스용 One Drive Win32 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="d4781-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="d4781-484">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-484">None</span></span>|<span data-ttu-id="d4781-485">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-485">None</span></span>|<span data-ttu-id="d4781-486">DLP 정책 팁은 Sharepoint 또는 데스크톱 클라이언트 앱에서 OneDrive 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="d4781-487">**Word, Excel, PowerPoint 웹 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="d4781-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="d4781-488">모두</span><span class="sxs-lookup"><span data-stu-id="d4781-488">All</span></span>|<span data-ttu-id="d4781-489">DLP의 모든 SPO/ODB 프레디트 및 작업</span><span class="sxs-lookup"><span data-stu-id="d4781-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="d4781-490">문서가 SPO 또는 ODB 웹앱에 호스트되어 있으며 DLP 정책이 이미 스탬프 처리된 경우 DLP 정책 팁이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="d4781-491">**Word, Excel, PowerPoint Mobile 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="d4781-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="d4781-492">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-492">None</span></span>|<span data-ttu-id="d4781-493">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-493">None</span></span>|<span data-ttu-id="d4781-494">DLP 정책 팁은 모바일 앱에 지원되지 Office.</span><span class="sxs-lookup"><span data-stu-id="d4781-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="d4781-495">**Teams Web/Teams Desktop/Teams Mobile/Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="d4781-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="d4781-496">모두</span><span class="sxs-lookup"><span data-stu-id="d4781-496">All</span></span>|<span data-ttu-id="d4781-497">DLP Teams 모든 Teams</span><span class="sxs-lookup"><span data-stu-id="d4781-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="d4781-498">정책 팁은 메시지가 "이 메시지에 플래그가 지정된 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="d4781-499">어떻게 해야 나요?"</span><span class="sxs-lookup"><span data-stu-id="d4781-499">What can I do?”</span></span> <span data-ttu-id="d4781-500">링크를 클릭할 때 사용자는 감지된 중요한 정보 유형을 검토하고 관리자가 허용하는 경우 문제를 재지정하거나 보고할 수 있습니다. 파일에 대한 정책 팁은 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="d4781-501">받는 사람이 문서에 액세스하는 경우 허용되지 않는 경우 액세스가 거부될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="d4781-502">**Win32 끝점 장치**</span><span class="sxs-lookup"><span data-stu-id="d4781-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="d4781-503">하위 집합</span><span class="sxs-lookup"><span data-stu-id="d4781-503">Subset</span></span>|<span data-ttu-id="d4781-504">DLP 정책의 모든 끝점 DLP 사문자 및 작업</span><span class="sxs-lookup"><span data-stu-id="d4781-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="d4781-505">일부 중요한 정보 유형에 대한 정책 팁 지원 끝점의 데이터 손실 [방지를 참조하세요.](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="d4781-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="d4781-506">**Mac 장치**</span><span class="sxs-lookup"><span data-stu-id="d4781-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="d4781-507">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-507">None</span></span>|<span data-ttu-id="d4781-508">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-508">None</span></span>|<span data-ttu-id="d4781-509">데이터 손실 방지 정책은 현재 Mac 장치에서 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="d4781-510">**제3자 클라우드 앱**</span><span class="sxs-lookup"><span data-stu-id="d4781-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="d4781-511">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-511">None</span></span>|<span data-ttu-id="d4781-512">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-512">None</span></span>|<span data-ttu-id="d4781-513">데이터 손실 방지 정책 팁은 제3자 클라우드 앱에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="d4781-514">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="d4781-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="d4781-515">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-515">None</span></span>|<span data-ttu-id="d4781-516">없음</span><span class="sxs-lookup"><span data-stu-id="d4781-516">None</span></span>||
|<span data-ttu-id="d4781-517">**Word, Excel, PowerPoint Win32 Client**</span><span class="sxs-lookup"><span data-stu-id="d4781-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="d4781-518">하위 집합</span><span class="sxs-lookup"><span data-stu-id="d4781-518">Subset</span></span>|<span data-ttu-id="d4781-519">하위 집합</span><span class="sxs-lookup"><span data-stu-id="d4781-519">Subset</span></span>|<span data-ttu-id="d4781-520">지원되는 중요한 정보 유형 목록에 대한 일부 중요한 정보 유형에 대한 정책 팁만 보여 Outlook [2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) 이상 및 데스크톱의 Office 앱을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4781-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="d4781-521">WXP 클라이언트 앱에 대한 정책 팁은 아래 또는 DLP 정책에 조건 또는 작업의 하위 집합이 있는 모든 DLP 정책에 대해 Sharepoint Online 또는 비즈니스용 One Drive 사이트에 저장된 문서에 대해 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4781-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="d4781-522">콘텐츠에 중요한 정보 유형 포함</span><span class="sxs-lookup"><span data-stu-id="d4781-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="d4781-523">액세스 범위(콘텐츠가 내부/외부적으로 공유)</span><span class="sxs-lookup"><span data-stu-id="d4781-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="d4781-524">사용자에게 알림(정책 팁/사용자 알림)</span><span class="sxs-lookup"><span data-stu-id="d4781-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="d4781-525">모든 사람 차단</span><span class="sxs-lookup"><span data-stu-id="d4781-525">Block everyone</span></span></li><li><span data-ttu-id="d4781-526">사고 보고서</span><span class="sxs-lookup"><span data-stu-id="d4781-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="d4781-527">다른 조건이나 작업이 있는 경우 해당 정책에 대한 DLP 정책 팁이 Word, Excel 또는 PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d4781-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="d4781-528">자세한 내용은 Excel, PowerPoint [및 Word의](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) 정책 팁을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4781-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
