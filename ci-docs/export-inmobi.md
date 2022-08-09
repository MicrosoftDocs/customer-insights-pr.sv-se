---
title: Exportera Customer Insights-data till InMobi
description: Lär dig att konfigurera anslutningen och exporten till InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195910"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Exportera Customer Insights-data till InMobi (förhandsversion)

Exportera segmentlistor eller andra data från din Customer Insights-instans till [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Förutsättningar

- Ett [InMobi-konto](https://www.inmobi.com/) och administratörsuppgifter.
- Ett [Azure Blob Storage-konto](/azure/storage/blobs/create-data-lake-storage-account) namn och kontonyckel. För att hitta namnet och nyckeln, se [Hantera inställningar för lagringskonto i Azure-portalen](/azure/storage/common/storage-account-manage).
- En [Azure Blob Storage behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) att exportera InMobi data till.
- InMobi skapar en direkt anslutning till din Blob Storage och konfigurerar en automatisk import av dina data till InMobi. Kontakta din InMobi-representant och påbörja processen.

## <a name="known-limitations"></a>Kända begränsningar

- För Azure Blob Storage kan du välja mellan [Nivåerna standardprestanda och premium-prestanda](/azure/storage/blobs/storage-blob-performance-tiers). Om du väljer prestandanivån Premium väljer du [premium blockblobb som kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Upprätta anslutningen till Azure Blob Storage

[Upprätta anslutningen till Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfigurera en export

[Konfigurera en export](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
