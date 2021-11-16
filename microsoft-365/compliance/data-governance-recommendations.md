---
title: 데이터 거버넌스 권장 사항을 표시하기 위해 콘텐츠가 식별되는 방법
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
ms.custom: admindeeplinkDEFENDER
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 'Microsoft 365 보안 센터 및 Microsoft 365 규정 준수 센터에서는 조직의 현재 설정을 기반으로 데이터 거버넌스 권장 사항을 제공하며, 몇 번의 클릭으로 설정을 완료할 수 있습니다. 이 권장 사항의 일부는 조직 내의 특정 콘텐츠를 검색한 후 해당 콘텐츠를 관리하는 단계별 방법을 권장합니다. 예를 들어, 권장 사항이 비즈니스 측면에서 중요한 콘텐츠(예: 비공개 유지 권한 또는 NDA 정보)가 포함된 항목을 검색할 수 있으며, 사용자는 해당 항목에 보존 레이블을 자동으로 적용하여 필요에 따라 해당 항목을 분류하고 보존할 수 있습니다. 이 항목에는 사용자가 확인할 수 있는 데이터 거버넌스 권장 사항이 나열되어 있으며, 각 권장 사항을 표시하기 위해 어떤 콘텐츠가 검색되는지 설명합니다.'
ms.openlocfilehash: f6343ab8856393f1928edfdb917e26fe9d72cc97
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963350"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>데이터 거버넌스 권장 사항을 표시하기 위해 콘텐츠가 식별되는 방법

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 보안 센터</a> 및 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>는 조직의 현재 설정에 따라 데이터 거버넌스에 대한 권장 사항을 제공하며, 단 몇 번의 클릭으로 이를 설정할 수 있도록 지원합니다. 이러한 권장 사항 중 일부는 조직의 특정 콘텐츠를 검색한 다음 해당 콘텐츠를 관리하기 위한 권장 단계를 제공합니다. 예를 들어 중요 비즈니스용 콘텐츠(예: 비공개 유지 권한 또는 NDA 정보)를 포함하는 항목을 검색한 다음 해당 항목에 보존 레이블을 자동으로 적용하여 필요에 따라 분류 및 보존되도록 할 수 있습니다.

이 항목에는 사용자가 확인할 수 있는 데이터 거버넌스 권장 사항이 나열되어 있으며 각 권장 사항을 표시하기 위해 어떤 콘텐츠가 검색되는지 설명합니다.

## <a name="clean-up-voicemail"></a>음성 사서함 정리

‘음성 메일’ 메시지 유형으로 식별된 전자 메일 메시지가 사용자의 사서함에서 감지되었을 때 이 권장 사항이 표시됩니다. [Exchange에서의 메시지 속성](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators#searchable-properties-in-exchange)에 대해 자세히 알아보세요.

## <a name="label-attorney-client-privilege-content"></a>비공개 유지 권한 콘텐츠 레이블 지정

다음 중 한 가지 조건이 충족되면 이 권장 사항이 표시됩니다.

- 전자 메일 메시지의 본문에서 다음 키워드 조합이 검색되는 경우:
  - ACP
  - 비공개 유지 권한
  - 비공개 유지 권한
  - 비공개 유지 권한

- SharePoint 또는 OneDrive 파일에서 다음 키워드 조합이 검색되는 경우:
  - ACP
  - 비공개 유지 권한*
  - AC 권한

## <a name="retain-audio-files"></a>오디오 파일 보존

SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>CAD 파일 보존

SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>이미지 파일 보존

SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>NDA 콘텐츠 보존

다음 중 한 가지 조건이 충족되면 이 권장 사항이 표시됩니다.

- 전자 메일 메시지의 본문에서 다음 키워드 조합이 검색되는 경우:
  - NDA
  - “비밀 유지 계약”
  - “비밀 유지 계약”

- SharePoint 또는 OneDrive의 .PDF 또는 .DOC 파일에서 다음 키워드 조합이 검색되는 경우:
  - NDA
  - 비밀 유지 계약

## <a name="retain-software-development-files"></a>소프트웨어 개발 파일 보존

SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>비디오 파일 보존

SharePoint 또는 OneDrive에서 다음 파일 형식이 검색되면 이 권장 사항이 표시됩니다.

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
