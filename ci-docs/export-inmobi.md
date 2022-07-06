---
title: Exportera Customer Insights-data till InMobi
description: Lär dig att konfigurera anslutningen och exporten till InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056552"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Exportera segmentlista och andra data till InMobi (förhandsgranskning)

Exportera segmentlistor eller andra data från din Customer Insights-instans till [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Förutsättningar

1. Du har ett [InMobi-konto](https://www.inmobi.com/) och administratörsuppgifter.
1. Du har ett Azure Blob Storage-kontot och motsvarande kontonyckel. Mer information finns i [Hantera inställningar för lagringskonto i Azure-portalen](/azure/storage/common/storage-account-manage). Det finns en behållare i lagringskontot som du kan exportera inMobi-data till. Mer information finns i [Skapa en behållare](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi skapar en direkt anslutning till din Blob Storage och konfigurerar en automatisk import av dina data till InMobi. Kontakta din InMobi-representant och påbörja processen.

## <a name="known-limitations"></a>Kända begränsningar

1. För Azure Blob Storage kan du välja mellan [Nivåerna standardprestanda och premium-prestanda](/azure/storage/blobs/storage-blob-performance-tiers). Om du väljer prestandanivån Premium väljer du [premium blockblobb som kontotyp](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Konfigurera anslutningen till Azure Blob Storage och konfigurera en export

1. Följ anvisningarna för att [konfigurera en anslutning till din Azure Blob Storage](export-azure-blob-storage.md).
2. Följ instruktionerna för att [konfigurera en export](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
