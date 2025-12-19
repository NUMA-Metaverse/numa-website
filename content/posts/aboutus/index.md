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

## 目的

現状、XR・メタバース系サークルは増加しているものの、メンバーが少なく、持続的な運営が難しい団体が少なからずあります。
このような状況下において、NUMAという全国的な共有基盤（共有財 / コモンズ）・活動領域は、各サークルの助けとなったり、1つのサークルで成し得ない規模のイベントの開催を可能にします。

**NUMAはそれぞれのサークルとしての価値を維持し、継続的な運営や発展を支援します。**

---

## 活動
NUMAでは、「サークル横断的」・「運営互助的」な活動を主体的に行っています。具体的には以下のような活動です。

* 全国学生VRサークル活動報告大会
* NUMA祭・V化祭（バーチャル合同文化祭）
  * 年に1度、サークルが合同で文化祭をバーチャルで開催します。
  * 2026年の開催は高校生の団体（JVSL）とも協力し、より大きな祭りを催します。
* 仮想学生集会
  * [Xで検索](https://x.com/hashtag/%E4%BB%AE%E6%83%B3%E5%AD%A6%E7%94%9F%E9%9B%86%E4%BC%9A?src=hashtag_click)
* 運営交流会
  * 月に1度、運営に興味あるメンバーが集まり、交流しています。
* LT会
* ヌマッカソン
  * NUMA + ハッカソン
  * 協賛様からご支援いただくことも。

ほかにも、物理空間のイベントへの参加も行っています。2025年12月には、XR Kaigi 2025に参加し、NUMAの関係者は約20名参加、そのうち3名がセッション登壇をしました（[**XR Kaigi 2025 セッション登壇**](/posts/blogs/xrkaigi2025)）。

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

2025-12-06 更新