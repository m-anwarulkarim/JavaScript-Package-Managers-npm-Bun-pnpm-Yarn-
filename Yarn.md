এক সময় NPM খুব ধীরগতির ছিল বলে ফেসবুক (এখন Meta) এই Yarn তৈরি করেছিল। এটি বর্তমানে অত্যন্ত স্থিতিশীল এবং অনেক বড় বড় প্রজেক্টে ব্যবহৃত হয়।

নিচে ধাপে ধাপে Yarn ব্যবহারের নিয়ম দেওয়া হলো:

---

### ১. Yarn ইনস্টল করা (Installation)

বর্তমানে Yarn ব্যবহারের সবচেয়ে আধুনিক পদ্ধতি হলো **Corepack** ব্যবহার করা (এটি Node.js এর সাথেই আসে)।

- **Corepack এনাবল করে ইনস্টল (সুপারিশকৃত):**

```bash
corepack enable
corepack prepare yarn@stable --activate

```

- **অথবা NPM দিয়ে গ্লোবাল ইনস্টল:**

```bash
npm install --global yarn

```

ইনস্টল হয়েছে কি না যাচাই করতে লিখুন: `yarn -v`

---

### ২. প্রজেক্ট শুরু করা (Initialize)

নতুন প্রজেক্ট সেটআপ করার জন্য টার্মিনালে লিখুন:

```bash
yarn init

```

এটি আপনাকে কিছু প্রশ্ন করবে এবং শেষে একটি `package.json` ফাইল তৈরি করবে। (সব ডিফল্ট রাখতে চাইলে `yarn init -y` দিতে পারেন)।

---

### ৩. প্যাকেজ ম্যানেজমেন্ট (Commands)

Yarn-এর কমান্ডগুলো NPM থেকে কিছুটা আলাদা কিন্তু খুবই সহজ:

- **প্যাকেজ যোগ করা (npm install-এর বদলে):**

```bash
yarn add <package-name>

```

- **ডেভ-ডিপেন্ডেন্সি হিসেবে যোগ করা:**

```bash
yarn add <package-name> --dev

```

- **সব ডিপেন্ডেন্সি ইনস্টল করা:**

```bash
yarn install
# অথবা শুধু
yarn

```

- **প্যাকেজ আপডেট করা:**

```bash
yarn upgrade <package-name>

```

- **প্যাকেজ রিমুভ করা:**

```bash
yarn remove <package-name>

```

---

### ৪. স্ক্রিপ্ট রান করা (Running Scripts)

আপনার `package.json` ফাইলের স্ক্রিপ্টগুলো চালাতে `run` ব্যবহার করতে হয়:

```bash
yarn run dev
# অথবা সংক্ষেপে
yarn dev

```

---

### ৫. Yarn-এর বিশেষ বৈশিষ্ট্য

- **Yarn Lock:** এটি `yarn.lock` ফাইল তৈরি করে যা নিশ্চিত করে যে আপনার টিমের সবাই ঠিক একই ভার্সনের প্যাকেজ ব্যবহার করছে।
- **Parallel Installation:** Yarn একসাথে অনেকগুলো প্যাকেজ ডাউনলোড করতে পারে, যা কাজ দ্রুত করে।
- **Offline Cache:** একবার কোনো প্যাকেজ ডাউনলোড করলে সেটি ক্যাশ-এ জমা থাকে, তাই ইন্টারনেট ছাড়াও পরে ওই প্যাকেজ ইনস্টল করা যায়।
- **Zero Installs (Yarn Berry/v2+):** এটি একটি অ্যাডভান্সড ফিচার যেখানে `node_modules` ছাড়াই প্রজেক্ট চালানো যায় (প্যাকেজগুলো জিপ আকারে থাকে)।

---

### সারসংক্ষেপ: NPM vs Bun vs PNPM vs Yarn

| কমান্ড         | NPM                 | Bun             | PNPM             | Yarn             |
| -------------- | ------------------- | --------------- | ---------------- | ---------------- |
| **Install**    | `npm install`       | `bun install`   | `pnpm install`   | `yarn install`   |
| **Add Pkg**    | `npm i <pkg>`       | `bun add <pkg>` | `pnpm add <pkg>` | `yarn add <pkg>` |
| **Run Script** | `npm run dev`       | `bun run dev`   | `pnpm dev`       | `yarn dev`       |
| **Lockfile**   | `package-lock.json` | `bun.lockb`     | `pnpm-lock.yaml` | `yarn.lock`      |

---

**পরামর্শ:** আপনি যদি **সবচেয়ে দ্রুতগতি** চান, তবে **Bun** ব্যবহার করুন। যদি **ডিস্ক স্পেস বাঁচাতে** চান, তবে **pnpm** ব্যবহার করুন। আর যদি একটি **স্থায়ী এবং ইন্ডাস্ট্রি স্ট্যান্ডার্ড** টুল চান, তবে **Yarn** বা **NPM** ব্যবহার করতে পারেন।
