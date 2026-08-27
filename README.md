# erendev-claude-skills

Bir proje fikrini; değerlendirme → tasarım yönü → proje dokümanı sırasıyla
olgunlaştıran, birbirine bağlanabilen 3 Claude Code skill'i.

[🇬🇧 English version below](#erendev-claude-skills-english)

---

## Skill'ler

| Skill | Ne yapar | Varsa okuduğu dosya | Yazdığı dosya |
|---|---|---|---|
| `idea-interrogator` | Fikrini kapsam, uygulanabilirlik, zaman/değer, amaç, beklenti ve özellikler açısından sorgular. Sonunda net bir GO/NO-GO kararı verir. | — | `idea-interrogator-verdict.md` |
| `visual-identity` | Referanslar, ruh hali ve karşılaştırmalarla derinlemesine bir "zevk röportajı" yapıp klişe olmayan bir görsel yön belirler. | `idea-interrogator-verdict.md` | `visual-identity.md` |
| `project-brief` | Doğrulama Özeti ve Tasarım Yönü bölümlerini de içeren, PRD tarzında bir proje dokümanı yazar. | `idea-interrogator-verdict.md`, `visual-identity.md` | `<proje-adı>-brief.md` |

### Skill'ler tek tek ne işe yarar?

**1. `idea-interrogator` — Fikrini sorgular**
Yeni bir proje fikrin olduğunda, sana tek tek sorular sorarak fikri zorlar:
kapsamı net mi, gerçekten yapılabilir mi, harcayacağın zamana değer mi,
amacı ne, "bitti" ne demek, hangi özellikler gerçekten gerekli? Cevapların
belirsizse üstüne gider. Sonunda "yap", "yapma" veya "şunları değiştirerek
yap" şeklinde net bir tavsiye verir — ama seni asla durdurmaz, karar hep
sende kalır.

**2. `visual-identity` — Görsel yönünü belirler**
Projenin arayüzünün nasıl görüneceğine karar vermene yardım eder: hangi
fontlar, hangi renkler, hangi his. Amaç, tipik "yapay zeka görünümlü"
tasarımlardan (mavi-mor gradyanlar, klasik sistem fontu, her yerde yuvarlak
köşeler) kaçınmak. Bunun için sana beğendiğin gerçek uygulama/marka/nesne
örnekleri sorar, ruh hali kelimeleri sorar, "şu mu bu mu" tarzında seçimler
sunar — ve sonunda hem yazılı bir açıklama hem de doğrudan kullanılabilecek
renk kodları/font isimleri gibi somut değerler verir.

**3. `project-brief` — Her şeyi tek dokümanda toplar**
Önceki iki skill'in çıktısı varsa onları okuyup tekrar sormaz; yoksa
gereken soruları kendisi sorar. Sonunda klasik bir PRD'nin (Genel Bakış,
Hedefler, Özellikler, Kapsam Dışı vb.) yanında iki ekstra bölüm daha içeren
bir proje dokümanı yazar: **Doğrulama Özeti** (idea-interrogator'dan) ve
**Tasarım Yönü** (visual-identity'den).

Her skill tek başına da çalışır — "okuduğu dosya" sütunu bir kısayoldur,
zorunluluk değildir.

## Kurulum

İstediğin skill klasörünü Claude Code'un skill dizinine kopyala:

```bash
cp -r idea-interrogator ~/.claude/skills/
cp -r visual-identity ~/.claude/skills/
cp -r project-brief ~/.claude/skills/
```

(Sadece tek bir projede kullanmak istersen o projenin `.claude/skills/`
klasörüne kopyalayabilirsin.)

## Örnek kullanım akışı

```
cd yeni-projem/
# 1. Fikri sorgula
claude "idea-interrogator kullan: <fikrini anlat>"
# → idea-interrogator-verdict.md yazılır

# 2. Görsel yönü belirle
claude "bu proje için visual-identity kullan"
# → visual-identity.md yazılır

# 3. Proje dokümanını oluştur
claude "project-brief kullan"
# → yukarıdaki iki dosyayı da kullanarak <proje-adı>-brief.md yazılır
```

## Lisans

MIT — bkz. [LICENSE](LICENSE).

---

## erendev-claude-skills (English)

Three chainable Claude Code skills for turning a raw idea into a validated,
designed, documented project brief.

### Skills

| Skill | Does | Reads (if present) | Writes |
|---|---|---|---|
| `idea-interrogator` | Interviews you on scope, doability, time/worth, purpose, expectations, features. Ends in a GO/NO-GO verdict. | — | `idea-interrogator-verdict.md` |
| `visual-identity` | Deep taste interview (references, mood, comparisons) to pick a non-generic visual direction. | `idea-interrogator-verdict.md` | `visual-identity.md` |
| `project-brief` | Writes a PRD-style brief, including Validation Summary and Design Direction sections. | `idea-interrogator-verdict.md`, `visual-identity.md` | `<project-name>-brief.md` |

Each skill works standalone — the "reads" column is a shortcut, not a
requirement.

### Install

Copy the folder for whichever skill(s) you want into your Claude Code skills
directory:

```bash
cp -r idea-interrogator ~/.claude/skills/
cp -r visual-identity ~/.claude/skills/
cp -r project-brief ~/.claude/skills/
```

(Or into a project's `.claude/skills/` to scope it to one repo.)

### Example workflow

```
cd my-new-project/
# 1. Validate the idea
claude "use idea-interrogator on: <describe your idea>"
# → writes idea-interrogator-verdict.md

# 2. Pick a visual direction
claude "use visual-identity for this project"
# → writes visual-identity.md

# 3. Generate the brief
claude "use project-brief"
# → writes <project-name>-brief.md, pulling in both files above
```

### License

MIT — see [LICENSE](LICENSE).
