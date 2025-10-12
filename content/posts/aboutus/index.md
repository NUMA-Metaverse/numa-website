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

Nippon Universities Metaverse Alliance (NUMA) は、全国のメタバースサークルの技術と情報を結集し、  
各サークルの活動を横断的に支援するために設立された、全国のメタバースサークルの連合体です。

現在 **14大学14団体** が加盟し、NUMA内で活動しています。
👉 [加盟団体を見る](/members)  

---

## 目的・活動

現状、メタバースサークルは増加しているものの、メンバーが少なく、持続的な運営が難しい団体が少なからずあります。
こうした団体に対して、NUMAという全国的なリソースの共有基盤があることにより、一つのサークルで成し得ないイベントの開催が可能になります。
NUMAは全国のメタバースサークルとしての価値を維持し、継続的な運営や発展を支援します。

NUMAでは毎月開催の定例会や、不定期にLT会やハッカソンなどのサークル横断的なイベントの企画が進行中です。

---

## 入会条件

下記の条件を満たす学生サークルは加盟申請が可能です。

- 現に存在する、または設立準備中の学生団体（非公認含む）  
- 団体の幹部その他の意思決定機関から加盟同意を得ていること  
- メタバース関連活動を行い、今後も継続する意思があること  

入会希望の場合は、
[NUMA 紹介資料](https://docs.google.com/document/d/1m6V6IItkijHTW4leKcfPeg1cJ25iKln2hkNFw69PJng/edit?usp=sharing)の **NUMAで活動するためには？** の項目をご確認のうえ、お手続きください。


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