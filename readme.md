# lfy

[doc-submission](https://docs.flathub.org/docs/for-app-authors/submission/)

```bash
# 更新requests
flatpak-pip-generator requests --yaml

# flatpak install org.gnome.Sdk org.gnome.Platform org.flatpak.Builder

# 检查yaml
flatpak run --command=flatpak-builder-lint org.flatpak.Builder manifest cool.ldr.lfy.yaml

# 构建安装
flatpak-builder --force-clean --sandbox --user --install --ccache \
  --mirror-screenshots-url=https://dl.flathub.org/media/ \
  --repo=repo builddir cool.ldr.lfy.yaml

# 检查仓库，appstream-missing-screenshots可忽略
flatpak run --command=flatpak-builder-lint org.flatpak.Builder repo repo
``