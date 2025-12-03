---
title: "NUMAについて"
date: 2025-10-10T00:00:00+09:00
draft: false
url: "/aboutus"
author: "NUMA"
tags: ["NUMA"]
categories: ["About"]
cover:
    image: "NUMALogo_Rectangle_Black_alpha_cut.svg"
---

# NUMAとは

NUMA (Nippon Universities Metaverse Alliance)は、日本全国のXR・メタバース系サークルの互助を実現する組織です。様々な知見を集積するだけでなく、お互いに切磋琢磨できる環境も実現します。

現在 **14大学14団体** が加盟し、NUMA内で活動しています。
👉 [加盟団体を見る](/members)  

---

## 目的・活動

現状、XR・メタバース系サークルは増加しているものの、メンバーが少なく、持続的な運営が難しい団体が少なからずあります。
こうした団体に対して、NUMAという全国的なリソースの共有基盤があることにより、1つのサークルで成し得ない規模のイベント開催が可能になります。
**NUMAはそれぞれのサークルとしての価値を維持し、継続的な運営や発展を支援します。**

NUMAでは毎月開催の定例会や、不定期にLT会やハッカソンなどのサークル横断的なイベントの企画が進行中です。

---

## より詳細な情報
詳細な入会条件も含め、本組織の詳細については、[**NUMA 紹介資料**](https://docs.google.com/document/d/1m6V6IItkijHTW4leKcfPeg1cJ25iKln2hkNFw69PJng/edit?usp=sharing)の 「NUMAで活動するためには？」 の項目をご確認ください。

また、上記リンクが使用できない場合やご不明な点がある場合は遠慮なく[Twitter NUMA公式アカウント](https://x.com/numa_meta_) へダイレクトメッセージをお送りください。  
（※DM受信を「全員に許可」に設定してください → [設定方法はこちら](https://help.twitter.com/ja/using-x/direct-messages#receive)）

<script>
new MutationObserver(() => {
  const isDark = document.body.classList.contains('dark');
  // 押した瞬間に切り替わるので逆にしないといけない
  const cover = document.querySelector('.entry-cover img');
  if (!cover) return;
  console.log(isDark)
  cover.src = (isDark) ? 'NUMALogo_Rectangle_White_alpha.svg' : 'NUMALogo_Rectangle_Black_alpha_cut.svg';
}).observe(document.body, { attributes: true, attributeFilter: ['class'] });
</script>