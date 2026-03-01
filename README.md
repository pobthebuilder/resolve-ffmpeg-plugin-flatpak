flatpak-builder --disable-rofiles-fuse --force-clean .build-dir com.blackmagic.ResolveStudio.ioplugin.ffmpeg_encoder_plugin.dvcp.bundle.yaml
sed -Ei 's/name=(.+)_dvcp_bundle/name=\1.dvcp.bundle/g' .build-dir/metadata
flatpak build-export --arch=x86_64 --update-appstream '--exclude=/lib/debug/*' --include=/lib/debug/app '--exclude=/share/runtime/locale/*/*' .repo .build-dir 1.0

