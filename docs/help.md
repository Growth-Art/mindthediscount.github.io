# Help & Support

Find step-by-step guides and tips to get the most out of your discount display app.  
This page includes:
- 📚 Link to full documentation
- ⚡ Setup for **Online Store 2.0** themes (recommended)
- 🛠 Manual setup for **non–Online Store 2.0** themes
- 💬 How to contact support

---

## 📚 Documentation
- **Full docs:** Add the link to your public documentation site here.  
  *(Example: help.mindthediscount.com)*

---

## ✅ Online Store 2.0 (Recommended)
1. Go to **Online Store → Themes → Customize**.
2. Open your **Product template**.
3. **Add block → Mind the Discount**.
4. Position the block and **Save/Publish**.

---

## 🛠 Manual Setup (For Non–Online Store 2.0 Themes)

If your theme does not support App Blocks, manually insert the Discount Widget:

### 1️⃣ Add the Discount Script
In your `theme.liquid` file, before the closing `</body>` tag, add:

```liquid
<script src="https://lionfish-app-fcv2v.ondigitalocean.app/assets/discount.js"></script>
```

---

### 2️⃣ Add the Discount Block Container
In your `product.liquid` file (or the product template used by your theme), insert this where you want the widget to appear:

```liquid
<div id="manual-discount-block"></div>
```

---

### 3️⃣ Pass Product Data to the Script
Right below the `<div>` you added, include:

```liquid
<script>
  window.productId = {{ product.id | json }};
  window.productPrice = {{ product.price | money_without_currency }};
  window.productCollections = {{ product.collections | map: 'id' | json }}.map(id => id.toString());
  window.shopDomain = "{{ shop.permanent_domain }}";
</script>
```

---

### 4️⃣ Save & Test
- Save all modified files.
- Refresh a product page on your storefront.
- The Discount Widget should appear in the chosen position.

!!! note "Tip"
    Even with manual placement, you can still customize design, visibility rules, and priority from the **Discount Detail** page in the app.

---

## 💬 Contact Support
- **Live chat:** Use the “Chat with us” button in the app.
- **Email:** support@mindthediscount.com

<img width="1224" height="701" alt="Ekran Resmi 2025-08-12 10 40 41" src="https://github.com/user-attachments/assets/8e8bc5f3-03de-481f-a4d4-b7235858c7ac" />
