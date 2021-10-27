---
title: 커넥트 DNS 레코드를 이름 확인에 Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
ms.assetid: 54ae2002-b38e-43a1-82fa-3e49d78fda56
description: Microsoft용 Namecheap에서 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online 및 기타 서비스에 대한 DNS 레코드를 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 31938656e17104d1388b53c05b6ccf3af9afc30f
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587032"
---
# <a name="connect-your-dns-records-at-namecheap-to-microsoft-365"></a>커넥트 DNS 레코드를 이름 확인에 Microsoft 365

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
DNS 호스팅 공급자로 Namecheap을 사용하고 있는 경우 이 문서의 단계에 따라 도메인을 확인하고 전자 메일, 비즈니스용 Skype Online에 대한 DNS 레코드를 설정하세요.
  
Namecheap에서 이러한 레코드를 추가하고 나면 도메인이 사용자 도메인과 함께 작동하게 Microsoft 서비스.
  
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-a-txt-record-for-verification"></a>확인을 위해 TXT 레코드 추가

Microsoft에서 사용자 도메인을 사용하려면 먼저 도메인을 소유하고 있어야 합니다. 도메인 등록 기관에서 사용자의 계정으로 로그인하고 DNS 레코드를 만들 수 있으면 Microsoft에 도메인을 소유하고 있음을 증명할 수 있습니다.
  
> [!NOTE]
> 이 레코드는 사용자가 도메인을 소유하고 있는지 확인하는 데만 사용되며 그 밖에 아무런 영향도 주지 않습니다. 원하는 경우 나중에 삭제할 수 있습니다. 
  
1. 시작하려면 이 링크를 사용하여 Namecheap의 도메인 [페이지로 이동합니다.](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) 로그인 및 계속하라는 메시지가 표시될 것입니다.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap에 로그인합니다.":::

1. 방문 페이지의 계정 아래 **드롭다운** 목록에서 도메인 목록을 선택합니다.  

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="드롭다운 목록에서 도메인 목록을 선택합니다.":::

1. 도메인 목록 페이지에서 편집할 도메인을 선택한 다음 관리를 **선택합니다.**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="관리를 선택합니다.":::

1. 고급 **DNS 를 선택합니다.**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="고급 DNS를 선택합니다.":::

1. 호스트 **레코드 섹션에서** 새 **레코드 추가를 선택합니다.**

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="새 레코드 추가를 선택합니다.":::

1. 유형 **드롭다운에서** **TXT 레코드 를 선택합니다.**
    
    > [!NOTE]
    > 새 **레코드** 추가를 선택하면 유형 **드롭다운이 자동으로 나타납니다.** 

     :::image type="content" source="../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png" alt-text="TXT 레코드를 선택합니다.":::

1. 새 레코드의 상자에서 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    (드롭다운 목록에서 **TTL** 값을 선택합니다.) 
    
    |**유형**|**호스트**|**Value(값)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |MS=ms *XXXXXXXX*  <br/>**참고:** 이 값은 예시입니다. 여기에는 표에 있는 특정 **대상 또는 주소 가리키기** 값을 사용합니다.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md) |30분  <br/> |

     :::image type="content" source="../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png" alt-text="표의 값을 복사하여 붙여넣습니다.":::

1. 변경 내용 **저장(확인** 표시) 컨트롤을 선택합니다. 

     :::image type="content" source="../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png" alt-text="변경 내용 저장 컨트롤을 선택합니다.":::

1. 방금 만든 레코드가 인터넷에서 업데이트될 수 있도록 몇 분 정도 기다립니다.
    
이제 도메인 등록 기관에 레코드가 추가되었습니다. Microsoft로 돌아가서 레코드를 요청합니다. Microsoft에서 올바른 TXT 레코드를 찾으면 도메인이 확인된 것입니다. 

다음을 통해 레코드를 Microsoft 365.
  
1. 관리 센터에서 도메인 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**로 이동하세요.**</a>
    
1. 도메인 페이지에서 확인할 도메인을 선택하고 설정 시작 **을 선택합니다.** 

    :::image type="content" source="../../media/dns-IONOS/IONOS-DomainConnects-2.png" alt-text="설치 시작을 선택합니다.":::

1. 계속을 **선택합니다.**
  
1. **도메인 확인** 페이지에서 **확인** 을 선택합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>사용자 도메인의 전자 메일이 Microsoft로 전송되도록 MX 레코드 추가하기
  
1. 시작하려면 이 링크를 사용하여 Namecheap의 도메인 [페이지로 이동합니다.](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) 로그인 및 계속하라는 메시지가 표시될 것입니다.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap에 로그인합니다.":::

1. 방문 페이지의 계정 아래 **드롭다운** 목록에서 도메인 목록을 선택합니다.  

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="드롭다운 목록에서 도메인 목록을 선택합니다.":::

1. 도메인 **목록 페이지에서** 편집할 도메인을 선택한 다음 관리를 **선택합니다.**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="관리를 선택합니다.":::

1. 고급 **DNS 를 선택합니다.**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="고급 DNS를 선택합니다.":::

1. 메일 **설정 섹션의** 전자 메일 전달  드롭다운 목록에서 사용자 지정 **MX를** 선택합니다. 
    
    (아래로 스크롤해야 할 수 있습니다.)

     :::image type="content" source="../../media/40199e2c-42cf-4c3f-9936-3cbe5d4e81a4.png" alt-text="사용자 지정 MX를 선택합니다."::: 

1. 새 **레코드 추가를 선택합니다.**

     :::image type="content" source="../../media/8d169b81-ba48-4d51-84ea-a08fa1616457.png" alt-text="새 레코드를 추가합니다.":::

1. 새 레코드의 상자에 다음 표의 값을 입력하거나 복사하여 붙여넣습니다.
    
    우선 **순위 상자는** 값 상자 오른쪽의 이름 없는 **상자입니다.** 드롭다운 목록에서 **TTL** 값을 선택합니다.) 
    
    |**유형**|**호스트**|**Value(값)**|**Priority(우선 순위)**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX 레코드  <br/> |@  <br/> |\<*domain-key*\>.mail.protection.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> **참고:** Microsoft  *\<domain-key\>*  계정에서 다운로드하세요.  [이 값을 찾는 방법](../get-help-with-domains/information-for-dns-records.md)          |0  <br/> 우선 순위에 대한 자세한 내용은 [MX 우선 순위란?](../setup/domains-faq.yml)을 참조하세요. <br/> |30분  <br/> |

     :::image type="content" source="../../media/f3b76d62-5022-48c1-901b-8615a8571309.png" alt-text="표의 값을 복사하여 붙여넣습니다.":::

1. 변경 내용 **저장(확인** 표시) 컨트롤을 선택합니다. 

     :::image type="content" source="../../media/ef4e3112-36d2-47c8-a478-136a565dd71d.png" alt-text="변경 내용 저장 컨트롤을 선택합니다.":::

1. 다른 MX 레코드가 있으면 다음 2단계 절차를 사용하여 각 레코드를 제거합니다.
    
    먼저 제거할  레코드에 대해 삭제(휴지통)를 선택합니다. 

     :::image type="content" source="../../media/7a7a751f-29c2-495f-8f55-98ca37ce555a.png" alt-text="삭제를 선택합니다.":::

    둘째, **예를** 선택하여 지우기 확인을 선택합니다. 

     :::image type="content" source="../../media/85ebc0c7-8787-43ee-9e7b-647375b3345c.png" alt-text="예를 선택합니다.":::

    이 절차의 앞부분에서 추가한 MX 레코드를 제외한 모든 MX 레코드를 제거합니다.
  
## <a name="add-the-cname-record-required-for-microsoft"></a>Microsoft에 필요한 CNAME 레코드 추가

1. 시작하려면 이 링크를 사용하여 Namecheap의 도메인 [페이지로 이동합니다.](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) 로그인 및 계속하라는 메시지가 표시될 것입니다.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap에 로그인합니다.":::

1. 방문 페이지의 계정 아래 **드롭다운** 목록에서 도메인 목록을 선택합니다.  

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="도메인 목록을 선택합니다.":::

1. 도메인 **목록 페이지에서** 편집할 도메인을 선택한 다음 관리를 **선택합니다.**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="관리를 선택합니다.":::

1. 고급 **DNS 를 선택합니다.**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="고급 DNS를 선택합니다.":::

1. 호스트 **레코드 섹션에서** 새 **레코드 추가를 선택합니다.**

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="새 레코드 추가를 선택합니다.":::

1. 유형 **드롭다운에서** **CNAME 레코드 를 선택합니다.**
    
    > [!NOTE]
    > 새 **레코드** 추가를 선택하면 유형 **드롭다운이 자동으로 나타납니다.** 

     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="CNAME Record(CNAME 레코드)를 선택합니다.":::

1. 새 레코드의 빈 상자에서 **레코드 종류** 로 **CNAME** 을 선택한 후 다음 표의 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**유형**|**호스트**|**Value(값)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |자동  <br/> |

     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="표의 값을 복사하여 붙여넣습니다.":::

1. 변경 내용 **저장(확인** 표시) 컨트롤을 선택합니다. 

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="변경 내용 저장 컨트롤을 선택합니다.":::

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>전자 메일 스팸 방지에 유용한 SPF용 TXT 레코드 추가

> [!IMPORTANT]
> 도메인 한 개의 SPF에 둘 이상의 TXT 레코드가 있을 수 없습니다. 도메인에 둘 이상의 SPF 레코드가 있는 경우 전자 메일 오류를 비롯하여 배달 및 스팸 분류 문제가 발생할 수 있습니다. 도메인에 이미 SPF 레코드가 있는 경우 Microsoft의 새 SPF 레코드를 만들지 마세요. 대신 두 값 집합을 모두 포함하는 *단일*  SPF 레코드가 있도록 현재 레코드에 필요한 Microsoft 값을 추가합니다. 

1. 시작하려면 이 링크를 사용하여 Namecheap의 도메인 [페이지로 이동합니다.](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) 로그인 및 계속하라는 메시지가 표시될 것입니다.
    
1. 방문 페이지의 계정 아래 **드롭다운** 목록에서 도메인 목록을 선택합니다.  

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="도메인 목록을 선택합니다.":::

1. 도메인 **목록 페이지에서** 편집할 도메인을 선택한 다음 관리를 **선택합니다.**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="관리를 선택합니다.":::

1. 고급 **DNS 를 선택합니다.**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="고급 DNS를 선택합니다.":::

1. 호스트 **레코드 섹션에서** 새 **레코드 추가를 선택합니다.**

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="새 레코드 추가를 선택합니다.":::

1. 유형 **드롭다운에서** **TXT 레코드 를 선택합니다.**
    
    > [!NOTE]
    > 새 **레코드** 추가를 선택하면 유형 **드롭다운이 자동으로 나타납니다.** 

     :::image type="content" source="../../media/c5d1fddb-28b5-48ec-91c9-3e5d3955ac80.png" alt-text="TXT 레코드를 선택합니다.":::

1. 새 레코드의 상자에 다음 표의 다음 값을 입력하거나 복사하여 붙여넣습니다.
    
    (드롭다운 목록에서 **TTL** 값을 선택합니다.) 
    
    |**유형**|**호스트**|**Value(값)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **참고:** 모든 공백이 올바르게 유지되도록 이 항목을 복사하여 붙여 넣는 것이 좋습니다. |30분  <br/> |

     :::image type="content" source="../../media/ea0829f1-990b-424b-b26e-9859468318dd.png" alt-text="표의 값을 복사하여 붙여넣습니다.":::

1. 변경 내용 **저장(확인** 표시) 컨트롤을 선택합니다. 

     :::image type="content" source="../../media/f2846c36-ace3-43d8-be5d-a65e2c267619.png" alt-text="변경 내용 저장 컨트롤을 선택합니다.":::

## <a name="advanced-option-skype-for-business"></a>고급 옵션: 비즈니스용 Skype

조직에서 채팅, 전화 회의 및 화상 통화와 비즈니스용 Skype 같은 온라인 통신 서비스에도 이 옵션을 사용하는 Microsoft Teams. Skype 사용자 간 통신을 위한 SRV 레코드 2개와 사용자를 로그인하고 서비스에 연결하기 위한 CNAME 레코드 2개 등 4개 레코드가 필요합니다.

### <a name="add-the-two-required-srv-records"></a>필수 SRV 레코드 2개 추가

1. 시작하려면 이 링크를 사용하여 Namecheap의 도메인 [페이지로 이동합니다.](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) You'll be prompted to sign in.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap에 로그인합니다.":::

1. 방문 페이지의 계정 아래 **드롭다운** 목록에서 도메인 목록을 선택합니다.  

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="도메인 목록을 선택합니다.":::

1. 도메인 **목록 페이지에서** 편집할 도메인을 선택한 다음 관리를 **선택합니다.**

     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="관리를 선택합니다.":::

1. 고급 **DNS 를 선택합니다.**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="고급 DNS를 선택합니다.":::

1. 호스트 **레코드 섹션에서** 새 **레코드 추가를 선택합니다.**

     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="새 레코드 추가를 선택합니다.":::

1. 유형 **드롭다운에서** **SRV 레코드 를 선택합니다.**
    
    > [!NOTE]
    > 새 **레코드** 추가를 선택하면 유형 **드롭다운이 자동으로 나타납니다.** 

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="SRV 레코드 유형을 선택합니다.":::

1. 새 레코드의 빈 상자에서 다음 표에 있는 첫 번째 행의 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**서비스**|**프로토콜**|**Priority(우선 순위)**|**Weight(가중치)**|**Port(포트)**|**대상**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |자동  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |자동  <br/> |
       
     :::image type="content" source="../../media/ff9566ea-0096-4b7f-873c-027080a23b56.png" alt-text="표의 값을 복사하여 붙여넣습니다.":::

1. 변경 내용 **저장(확인** 표시) 컨트롤을 선택합니다. 

     :::image type="content" source="../../media/48a8dee4-c66d-449d-8759-9e9784c82b13.png" alt-text="변경 내용 저장 컨트롤을 선택합니다.":::

1. 표의 두 번째 행에서 값을 선택하여 다른 SRV 레코드를 추가합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가 
  
1. 호스트 **레코드 섹션에서** 새 **레코드 추가를 선택합니다.**
    
     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="새 이름 추가를 선택합니다.":::

1. 유형 **드롭다운에서** **CNAME 을 선택합니다.**
    
    > [!NOTE]
    > 새 **레코드** 추가를 선택하면 유형 **드롭다운이 자동으로 나타납니다.** 

     :::image type="content" source="../../media/fd55cd7c-2243-4de1-8d39-2c3f7ea3ae51.png" alt-text="CNAME을 선택합니다.":::

1. 새 레코드의 빈 상자에 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**유형**|**호스트**|**Value(값)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |자동  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |자동  <br/> |

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="표의 CNAME 값을 복사하여 붙여넣습니다.":::

1. 변경 내용 **저장(확인** 표시) 컨트롤을 선택합니다. 

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="변경 내용 저장 컨트롤을 선택합니다.":::

1. 표의 두 번째 행에서 값을 선택하여 다른 CNAME 레코드를 추가합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 
  
## <a name="advanced-option-intune-and-mobile-device-management-for-microsoft-365"></a>고급 옵션: Intune 및 모바일 장치 관리 Microsoft 365

이 서비스는 도메인에 연결하는 모바일 장치를 보호하고 원격으로 관리하는 데 도움이 됩니다. 모바일 장치 관리에는 사용자가 서비스에 장치를 등록할 수 있도록 두 개의 CNAME 레코드가 필요합니다.

### <a name="add-the-two-required-cname-records"></a>두 개의 필수 CNAME 레코드 추가

1. 시작하려면 이 링크를 사용하여 Namecheap의 도메인 [페이지로 이동합니다.](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f) You'll be prompted to sign in.

     :::image type="content" source="../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png" alt-text="Namecheap에 로그인합니다.":::

1. 방문 페이지의 계정 아래 **드롭다운** 목록에서 도메인 목록을 선택합니다.  

     :::image type="content" source="../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png" alt-text="도메인 목록을 선택합니다.":::

1. 도메인 **목록 페이지에서** 편집할 도메인을 선택한 다음 관리를 **선택합니다.**
    
     :::image type="content" source="../../media/fb2020d8-707c-4148-835e-304ac6244d66.png" alt-text="관리를 선택합니다.":::

1. 고급 **DNS 를 선택합니다.**

     :::image type="content" source="../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png" alt-text="드롭다운 목록에서 DNS 레코드 관리를 선택합니다.":::

1. 호스트 **레코드 섹션에서** 새 **레코드 추가를 선택합니다.**
    
     :::image type="content" source="../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png" alt-text="새 레코드 추가를 선택합니다.":::

1. 유형 **드롭다운에서** **CNAME 레코드 를 선택합니다.**
    
    > [!NOTE]
    > 새 **레코드** 추가를 선택하면 유형 **드롭다운이 자동으로 나타납니다.** 
  
     :::image type="content" source="../../media/0898f3b2-06ab-4364-a86a-a603a25b39f4.png" alt-text="CNAME Record(CNAME 레코드)를 선택합니다.":::

1. 새 레코드의 빈 상자에 표의 첫 번째 행 값을 입력하거나 복사하여 붙여넣습니다.
    
    |**유형**|**호스트**|**Value(값)**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |자동  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **이 값은 마침표(.)로 끝나야 합니다.** <br/> |자동  <br/> |
       
     :::image type="content" source="../../media/f79c5679-34eb-4544-8517-caa2e8a4111a.png" alt-text="표의 값을 복사하여 붙여넣습니다.":::

1. 변경 내용 **저장 컨트롤을** 선택합니다. 

     :::image type="content" source="../../media/91a5cce4-ca41-41ec-b976-aafe681a4d68.png" alt-text="변경 내용 저장 컨트롤을 선택합니다.":::

1. 표의 두 번째 행에서 값을 선택하여 다른 CNAME 레코드를 추가합니다.
    
> [!NOTE]
> 일반적으로 DNS 변경 내용을 적용하는 데 15분 정도 걸립니다. 그러나 변경한 내용이 인터넷의 DNS 시스템 전체에 업데이트되는 데에는 시간이 오래 걸릴 수 있습니다. DNS 레코드를 추가한 후 메일 흐름이나 기타 문제가 있는 경우 [도메인 이름 또는 DNS 레코드 변경 후 발생한 문제 해결](../get-help-with-domains/find-and-fix-issues.md)을 참조하세요. 


