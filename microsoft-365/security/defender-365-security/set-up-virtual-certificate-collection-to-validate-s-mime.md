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
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072556"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>S/MIME의 유효성을 검사하기 위해 Exchange Online에서 가상 인증서 컬렉션 설정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


관리자는 S/MIME 인증서의 유효성을 검사하는 데 사용할 가상 인증서 컬렉션을 Exchange Online에서 구성해야 합니다. 이 가상 인증서 컬렉션은 SST 파일 이름 확장명을 통해 인증서 저장소로 설정됩니다. SST 파일에는 S/MIME 인증서 유효성을 검사할 때 사용되는 모든 루트 및 중간 인증서가 포함됩니다.

## <a name="create-and-save-an-sst"></a>SST 만들기 및 저장

이 SST 인증서 저장소 파일은 신뢰할 수 있는 컴퓨터의 **Export-Certificate** cmdlet을 사용하여 내보내고 Windows PowerShell  값을 SST로 지정하여 만들 수 있습니다. 자세한 내용은 [Export-Certificate를 참조하세요.](/powershell/module/pkiclient/export-certificate)

SST 인증서 저장소 파일이 있는 경우 Exchange Online PowerShell에서 다음 구문을 사용하여 SST 파일 콘텐츠를 Exchange Online 가상 인증서 저장소에 저장합니다. Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

이 예제에서는 SST 파일 C:\My Documents\Exported Certificate Store.sst를 가져오습니다.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

구문과 매개 변수에 대한 자세한 내용은 [Set-SmimeConfig 를 참조하십시오.](/powershell/module/exchange/set-smimeconfig)

## <a name="ensuring-a-certificate-is-valid"></a>인증서가 유효한지 확인

Exchange Online에서는 SST만 인증서 유효성 검사에 사용됩니다.

## <a name="more-information"></a>추가 정보

[메시지 서명 및 암호화를 위한 S/MIME](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)