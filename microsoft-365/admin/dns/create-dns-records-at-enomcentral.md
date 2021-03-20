---
title: eNomCentral에서 Microsoft용 DNS 레코드 만들기
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Microsoft용 eNomCentral에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 학습합니다.
ms.openlocfilehash: 528659667ee062c8cf767bed0989558020032924
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910369"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>eNomCentral에서 Microsoft용 DNS 레코드 만들기

 **원하는 정보는 찾지 못한 경우 [도메인 질문과 대답을 확인](../setup/domains-faq.yml)** 하세요.

DNS 호스팅 공급자로 eNomCentral을 사용하고 있는 경우, 이 문서에 나와 있는 단계를 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 등에 대한 DNS 레코드를 설정합니다.

eNomCentral에서 이러한 레코드를 추가하면 도메인이 Microsoft 서비스에서 작동할 수 있도록 설정됩니다.

> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.

## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가
<a name="BKMK_verify"> </a>

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.

> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다.

아래 단계를 따르거나 [비디오를 시청하세요(0:46에 시작)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 내 **도메인에서** 편집할 도메인의 이름을 선택합니다.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.

   드롭다운 **목록에서** 레코드 종류 값을 선택합니다.

   |호스트 이름|Record Type|주소|
   |---|---|---|
   |@|TXT|MS=ms *XXXXXXXX*  <br/> **참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. 저장을 **선택합니다.**

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.

이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft 365로 돌아가서 Microsoft 365에 레코드를 찾을 것을 요청합니다.

Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다.

1. Microsoft 관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 페이지로 이동합니다.

2. **도메인** 페이지에서 확인 중인 도메인을 선택합니다.

3. **설정** 페이지에서 **설정 시작** 을 선택합니다.

4. **도메인 확인** 페이지에서 **확인** 을 선택합니다.

> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
<a name="BKMK_add_MX"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(3:40에 시작)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 내 **도메인에서** 편집할 도메인의 이름을 선택합니다.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Email Settings(전자 메일 설정)** 를 선택합니다.

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. **Service Selection**(서비스 선택) 드롭다운 목록에서 **User (MX)**(사용자(MX))를 선택합니다.

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. In the boxes for the new record, type or copy and paste the values from the following table.

   |호스트 이름|주소|기본 설정|
   |---|---|---|
   |@| *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> **참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요. [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)|10    <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요.|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. 저장을 **선택합니다.**

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. 기본의 다른 MX 레코드가 있으면 해당 레코드의 확인란을 선택하여 레코드를 선택합니다.

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. 선택된 **삭제를 선택합니다.**

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가하기
<a name="BKMK_add_CNAME"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(4:24에 시작)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 내 **도메인에서** 편집할 도메인의 이름을 선택합니다.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 새 **행을 선택합니다.**

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. 6개의 새 레코드 상자에서 다음 값을 입력하거나 복사하여 붙여넣습니다.

   드롭다운 **목록에서** 레코드 종류 값을 선택합니다.

   |호스트 이름|Record Type|주소|
   |---|---|---|
   |autodiscover|CNAME (Alias)(CNAME(별칭))|autodiscover.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.**|
   |sip|CNAME (Alias)(CNAME(별칭))|sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.**|
   |lyncdiscover|CNAME (Alias)(CNAME(별칭))|webdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.**|
   |enterpriseregistration|CNAME (Alias)(CNAME(별칭))|enterpriseregistration.windows.net.  <br/> **이 값은 마침표(.)로 끝나야 합니다.**|
   |enterpriseenrollment|CNAME (Alias)(CNAME(별칭))|enterpriseenrollment-s.manage.microsoft.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.**|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. 저장을 **선택합니다.**

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는  *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다.

아래 단계를 따르거나 [비디오를 시청하세요(5:12에 시작)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 내 **도메인에서** 편집할 도메인의 이름을 선택합니다.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.

   드롭다운 **목록에서** 레코드 종류 값을 선택합니다.

   |호스트 이름|Record Type|주소|
   |---|---|---|
   |@|TXT|v=spf1 include:spf.protection.outlook.com -all  <br/>**참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다.|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. 저장을 **선택합니다.**

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Microsoft 필요한 2개의 SRV 레코드 추가하기
<a name="BKMK_add_SRV"> </a>

아래 단계를 따르거나 [비디오를 시청하세요(5:50에 시작)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. 시작하려면 [이 링크](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered)를 사용하여 eNom Central의 도메인 페이지로 이동합니다. 로그인하라는 메시지가 표시됩니다.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. 내 **도메인에서** 편집할 도메인의 이름을 선택합니다.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. **Manage Domain(도메인 관리)** 드롭다운 목록에서 **Host Records(호스트 레코드)** 를 선택합니다.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. 새 행의 **오른쪽에서** **SRV** 또는 SPF 레코드 추가를 선택합니다.

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. 두 개의 새 레코드 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.

   |서비스|Protocol(프로토콜)|우선 순위|가중치|포트|대상(호스트 이름)|
   |---|---|---|---|---|---|
   |_sip|_tls|100|1|443|sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.**|
   |_sipfederationtls|_tcp|100|1|5061|sipfed.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.**|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. 저장 **선택**

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요.