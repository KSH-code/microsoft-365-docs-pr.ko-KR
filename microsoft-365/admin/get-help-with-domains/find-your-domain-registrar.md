---
title: Office 365의 도메인 등록 기관 찾기
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: InterNIC 검색을 사용하여 도메인 등록 기관 및 DNS 호스팅 공급자를 찾는 방법에 대해 알아보세요.
ms.openlocfilehash: 058eb4468e073b6929fbc763b3d9bdb189063213
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255134"
---
# <a name="find-your-domain-registrar-for-office-365"></a>Office 365의 도메인 등록 기관 찾기

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
## <a name="domain-registrar"></a>도메인 등록 기관
  
### <a name="find-your-domain-name-registrar"></a>도메인 이름 등록 기관 찾기

>[!NOTE]
> *.COM*, *.NET*, and *.EDU*로 끝나는 도메인만이 이 도구를 사용할 수 있습니다.
  
1. [InterNIC 검색 페이지](https://go.microsoft.com/fwlink/p/?LinkId=402770)의 **Whois Search(Whois 검색)** 상자에 도메인을 입력합니다. 예: *contoso.com.* 
    
2. **Domain(도메인)** 옵션을 선택하고 **Submit(제출)** 을 선택합니다.
    
3. **Whois Search Results(Whois 검색 결과)** 페이지에서 **Registrar(등록 기관)** 항목을 찾습니다. 이 항목에는 도메인에 등록 기관 서비스를 제공하는 조직이 나열됩니다. 
    
## <a name="dns-hosting-provider"></a>DNS 호스팅 공급자
  
### <a name="find-your-dns-hosting-provider"></a>DNS 호스팅 공급자 찾기

>[!NOTE]
> *.COM*, *.NET*, and *.EDU*로 끝나는 도메인만이 이 도구를 사용할 수 있습니다.
  
1. [InterNIC 검색 페이지]( https://go.microsoft.com/fwlink/p/?LinkId=402770)의 **Whois Search(Whois 검색)** 상자에 도메인을 입력합니다. 예로 contoso.com 등을 들 수 있습니다. 
    
2. **Domain(도메인)** 옵션을 선택하고 **Submit(제출)** 을 선택합니다.
    
3. 
            **Whois Search Results(Whois 검색 결과)** 페이지에서 첫 번째 **Name Server(이름 서버)** 항목을 찾습니다. 
    
4. 콜론(:) 뒤에 나타나는 NS(이름 서버) 정보를 복사하고 페이지 위쪽의 **검색** 상자에 붙여 넣습니다. **Nameserver(이름 서버)** 를 선택하고 **Submit(제출)** 을 클릭합니다.
    
5. 
            **Whois Search Results(Whois 검색 결과)** 페이지에서 **Registrar(등록 기관)** 항목을 찾습니다. 이 항목에는 DNS 호스팅 공급자, 즉 도메인의 이름 서버를 소유한 DNS 공급자가 나열됩니다. 
    
---

