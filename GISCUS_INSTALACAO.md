# 🎯 Instalação do Giscus - Passo a Passo

## ✅ Passo 1: Configuração no site do Giscus (você já está aqui!)

Na página do Giscus (https://giscus.app), você já selecionou:
- ✅ **Mapeamento**: "pathname" (correto!)

Agora complete:

1. **Repository**: `kleytonmr/Blogs-Like`
2. **Discussion Category**: Escolha uma categoria (ex: "Announcements" ou "General")
3. **Features**: Marque "Enable reactions" (Reações)
4. **Theme**: Escolha um tema (recomendo "Light" ou "preferred_color_scheme")
5. **Language**: `pt` (Português)

## 📋 Passo 2: Obter os IDs

Role até o final da página do Giscus e copie:

1. **data-repo-id**: Um código como `R_kgDOJ...`
2. **data-category-id**: Um código como `DIC_kwDOJ...`

## ⚙️ Passo 3: Atualizar o _config.yml

Abra o arquivo `_config.yml` e encontre a seção `giscus`. Preencha os IDs:

```yaml
giscus:
  repo: kleytonmr/Blogs-Like
  repo_id: "COLE_AQUI_O_REPO_ID"  # Exemplo: "R_kgDOJ..."
  category: "Announcements"  # ou a categoria que você escolheu
  category_id: "COLE_AQUI_O_CATEGORY_ID"  # Exemplo: "DIC_kwDOJ..."
  mapping: "pathname"
  reactions_enabled: "1"
  emit_metadata: "0"
  input_position: "bottom"
  theme: "light"  # ou "preferred_color_scheme" se preferir
  lang: "pt"
```

## 🔧 Passo 4: Verificar se o código está no layout

O arquivo `_layouts/post.html` já deve ter o código do Giscus no final. Verifique se existe esta seção:

```liquid
{% if site.giscus.repo_id != "" and site.giscus.category_id != "" %}
<div class="giscus-comments">
    <script src="https://giscus.app/client.js"
            data-repo="{{ site.giscus.repo }}"
            data-repo-id="{{ site.giscus.repo_id }}"
            ...
    </script>
</div>
{% endif %}
```

## 🚀 Passo 5: Instalar o Giscus App no GitHub

1. Acesse: https://github.com/apps/giscus
2. Clique em **"Install"** (Instalar)
3. Selecione seu repositório: **Blogs-Like**
4. Clique em **"Install"** novamente

## 💬 Passo 6: Ativar GitHub Discussions

1. Acesse: https://github.com/kleytonmr/Blogs-Like
2. Vá em **Settings** → **General**
3. Role até a seção **Features**
4. Marque **"Discussions"**
5. Clique em **"Set up discussions"**
6. Escolha um template ou deixe em branco
7. Clique em **"Start discussion"**

## ✅ Passo 7: Testar

1. Faça commit e push:
```bash
git add _config.yml
git commit -m "Configurar Giscus com IDs"
git push origin main
```

2. Aguarde o deploy (2-5 minutos)

3. Acesse qualquer post do blog

4. Role até o final - você deve ver a seção "Comentários" com o widget do Giscus

## 🎨 Personalização (Opcional)

Você pode alterar no `_config.yml`:

- **theme**: `"light"`, `"dark"`, `"preferred_color_scheme"`, ou `"transparent_dark"`
- **input_position**: `"top"` ou `"bottom"`
- **reactions_enabled**: `"1"` (sim) ou `"0"` (não)

## ❓ Problemas Comuns

### Comentários não aparecem
- Verifique se os IDs estão corretos no `_config.yml`
- Verifique se o Giscus App está instalado no repositório
- Verifique se GitHub Discussions está ativado
- Aguarde alguns minutos após o deploy

### Erro 404 nas discussões
- Verifique se GitHub Discussions está ativado
- Verifique se a categoria existe no repositório

---

**Próximo passo**: Cole os IDs que você copiou do Giscus no `_config.yml`!

