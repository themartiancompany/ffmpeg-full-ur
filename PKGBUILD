# Maintainer : Daniel Bermond <dbermond@archlinux.org>
# Contributor: Iacopo Isimbaldi <isiachi@rhye.it>

_svt_hevc_ver='1.4.3'
_svt_av1_ver='0.8.1'
_svt_vp9_ver='0.1.0'

pkgname=ffmpeg-full
pkgver=4.2.2
pkgrel=3
pkgdesc='Complete solution to record, convert and stream audio and video (all possible features including libfdk-aac)'
arch=('x86_64')
url='https://www.ffmpeg.org/'
license=('custom: nonfree and unredistributable')
depends=(
    # official repositories:
        'alsa-lib' 'bzip2' 'frei0r-plugins' 'libgcrypt' 'gmp' 'gnutls' 'ladspa' 'libass'
        'aom' 'aribb24' 'libbluray' 'libbs2b' 'libcaca' 'celt' 'libcdio-paranoia' 'codec2'
        'dav1d' 'libdc1394' 'libavc1394' 'libfdk-aac' 'fontconfig' 'freetype2' 'fribidi'
        'libgme' 'gsm' 'libiec61883' 'libilbc' 'jack' 'kvazaar' 'lensfun' 'libmodplug'
        'lame' 'opencore-amr' 'openjpeg2' 'opus' 'pulseaudio' 'librsvg' 'rubberband'
        'rtmpdump' 'snappy' 'libsoxr' 'speex' 'srt' 'libssh' 'svt-hevc' 'svt-av1' 'svt-vp9'
        'tensorflow' 'tesseract' 'libtheora' 'twolame' 'v4l-utils' 'vid.stab' 'vmaf'
        'libvorbis' 'libvpx' 'wavpack' 'libwebp' 'x264' 'x265' 'libxcb' 'xvidcore'
        'libxml2' 'zimg' 'zeromq' 'zvbi' 'lv2' 'lilv' 'xz' 'libmysofa' 'openal' 'ocl-icd'
        'libgl' 'sndio' 'sdl2' 'vapoursynth' 'libxv' 'libx11'  'libxext' 'zlib' 'cuda'
        'libomxil-bellagio' 'libdrm' 'intel-media-sdk' 'libva' 'libvdpau'
    # AUR:
        'chromaprint-fftw' 'davs2' 'flite1-patched' 'libklvanc-git' 'openh264'
        'libopenmpt-svn' 'shine' 'vo-amrwbenc' 'xavs' 'xavs2' 'pocketsphinx'
        'rockchip-mpp'
)
makedepends=(
    # official repositories:
        'nasm' 'opencl-headers' 'ffnvcodec-headers'
    # AUR:
        'decklink-sdk'
)
provides=('libavcodec.so' 'libavdevice.so' 'libavfilter.so' 'libavformat.so'
          'libavutil.so' 'libpostproc.so' 'libavresample.so' 'libswscale.so'
          'libswresample.so' 'ffmpeg')
conflicts=('ffmpeg')
source=("https://ffmpeg.org/releases/ffmpeg-${pkgver}.tar.xz"{,.asc}
        "ffmpeg-full-add-svt-hevc-${_svt_hevc_ver}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/v${_svt_hevc_ver}/ffmpeg_plugin/0001-lavc-svt_hevc-add-libsvt-hevc-encoder-wrapper.patch"
        "ffmpeg-full-add-svt-hevc-docs-${_svt_hevc_ver}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-HEVC/v${_svt_hevc_ver}/ffmpeg_plugin/0002-doc-Add-libsvt_hevc-encoder-docs.patch"
        "ffmpeg-full-add-svt-av1-${_svt_av1_ver}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-AV1/v${_svt_av1_ver}/ffmpeg_plugin/0001-Add-ability-for-ffmpeg-to-run-svt-av1-with-svt-hevc.patch"
        "ffmpeg-full-add-svt-vp9-${_svt_vp9_ver}.patch"::"https://raw.githubusercontent.com/OpenVisualCloud/SVT-VP9/v${_svt_vp9_ver}/ffmpeg_plugin/0001-Add-ability-for-ffmpeg-to-run-svt-vp9-with-svt-hevc-av1.patch"
        'ffmpeg-full-add-decklink-11.5-support.patch'::'https://git.ffmpeg.org/gitweb/ffmpeg.git/patch/f32f9231dd4f74d9f95eef575b838bdc3e06a234'
        'LICENSE')
sha256sums=('cb754255ab0ee2ea5f66f8850e1bd6ad5cac1cd855d0a2f4990fb8c668b0d29c'
            'SKIP'
            '878757eb6d7072521caaeb71f1453ec3fc0f91a12936ef302e1625184787c6a6'
            '1499e419dda72b1604dc5e3959668f3843292ff56bfba78734e31510ba576de0'
            'efbe348e0dad6b5f9fc501a34ff8304d82c2745ec9ac952e72f8549775c2fe78'
            '7690a4f6bdc4a57e35c7ff5b6e87f2fe6d056d452eff9e767eaccff41832f4d7'
            'd23dedb5a275d1d753d30fd544a46d5b609868ad5d384b9c8c2ecc1a02281828'
            '04a7176400907fd7db0d69116b99de49e582a6e176b3bfb36a03e50a4cb26a36')
validpgpkeys=('FCF986EA15E6E293A5644F10B4322F04D67658D8')

prepare() {
    # add svt codec support for hevc, av1 and vp9
    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/ffmpeg-full-add-svt-hevc-${_svt_hevc_ver}.patch"
    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/ffmpeg-full-add-svt-hevc-docs-${_svt_hevc_ver}.patch"
    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/ffmpeg-full-add-svt-av1-${_svt_av1_ver}.patch"
    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/ffmpeg-full-add-svt-vp9-${_svt_vp9_ver}.patch"
    
    # add decklink-sdk 11.5 support
    patch -d "ffmpeg-${pkgver}" -Np1 -i "${srcdir}/ffmpeg-full-add-decklink-11.5-support.patch"
}

build() {
    cd "ffmpeg-${pkgver}"
    
    local _ldflags='-L/opt/cuda/lib64'
    
    # set path of -lcuda on systems with legacy nvidia-340xx drivers
    # (libcuda.so.x, required by --enable-cuda-sdk)
    if pacman -Qs '^nvidia-340xx-utils' >/dev/null 2>&1
    then
        _ldflags+=' -L/usr/lib/nvidia'
    fi
    
    printf '%s\n' '  -> Running ffmpeg configure script...'
    
    ./configure \
        --prefix='/usr' \
        --extra-cflags='-I/opt/cuda/include -I/usr/include/tensorflow' \
        --extra-ldflags="$_ldflags" \
        \
        --disable-rpath \
        --enable-gpl \
        --enable-version3 \
        --enable-nonfree \
        --enable-shared \
        --disable-static \
        --disable-stripping \
        --enable-gray \
        --enable-avresample \
        \
        --enable-alsa \
        --enable-avisynth \
        --enable-bzlib \
        --enable-chromaprint \
        --enable-frei0r \
        --enable-gcrypt \
        --enable-gmp \
        --enable-gnutls \
        --enable-iconv \
        --enable-ladspa \
        --enable-libaom \
        --enable-libaribb24 \
        --enable-libass \
        --enable-libbluray \
        --enable-libbs2b \
        --enable-libcaca \
        --enable-libcelt \
        --enable-libcdio \
        --enable-libcodec2 \
        --enable-libdav1d \
        --enable-libdavs2 \
        --enable-libdc1394 \
        --enable-libfdk-aac \
        --enable-libflite \
        --enable-fontconfig \
        --enable-libfreetype \
        --enable-libfribidi \
        --enable-libgme \
        --enable-libgsm \
        --enable-libiec61883 \
        --enable-libilbc \
        --enable-libjack \
        --enable-libklvanc \
        --enable-libkvazaar \
        --enable-liblensfun \
        --enable-libmodplug \
        --enable-libmp3lame \
        --enable-libopencore-amrnb \
        --enable-libopencore-amrwb \
        --disable-libopencv \
        --enable-libopenh264 \
        --enable-libopenjpeg \
        --enable-libopenmpt \
        --enable-libopus \
        --enable-libpulse \
        --enable-librsvg \
        --enable-librubberband \
        --enable-librtmp  \
        --enable-libshine \
        --disable-libsmbclient \
        --enable-libsnappy \
        --enable-libsoxr \
        --enable-libspeex \
        --enable-libsrt \
        --enable-libssh \
        --enable-libsvthevc \
        --enable-libsvtav1 \
        --enable-libsvtvp9 \
        --enable-libtensorflow \
        --enable-libtesseract \
        --enable-libtheora \
        --disable-libtls \
        --enable-libtwolame \
        --enable-libv4l2 \
        --enable-libvidstab \
        --enable-libvmaf \
        --enable-libvo-amrwbenc \
        --enable-libvorbis \
        --enable-libvpx \
        --enable-libwavpack \
        --enable-libwebp \
        --enable-libx264 \
        --enable-libx265 \
        --enable-libxavs \
        --enable-libxavs2 \
        --enable-libxcb \
        --enable-libxcb-shm \
        --enable-libxcb-xfixes \
        --enable-libxcb-shape \
        --enable-libxvid \
        --enable-libxml2 \
        --enable-libzimg \
        --enable-libzmq \
        --enable-libzvbi \
        --enable-lv2 \
        --enable-lzma \
        --enable-decklink \
        --disable-mbedtls \
        --enable-libmysofa \
        --enable-openal \
        --enable-opencl \
        --enable-opengl \
        --disable-openssl \
        --enable-pocketsphinx \
        --enable-sndio \
        --enable-sdl2 \
        --enable-vapoursynth \
        --enable-xlib \
        --enable-zlib \
        \
        --enable-cuda-nvcc \
        --enable-cuvid \
        --enable-ffnvcodec \
        --enable-libdrm \
        --enable-libmfx \
        --enable-libnpp \
        --enable-nvdec \
        --enable-nvenc \
        --enable-omx \
        --enable-omx-rpi \
        --enable-rkmpp \
        --enable-v4l2-m2m \
        --enable-vaapi \
        --enable-vdpau
        
    make
    make tools/qt-faststart
}

package() {
    make -C "ffmpeg-${pkgver}" DESTDIR="$pkgdir" install
    install -D -m755 "ffmpeg-${pkgver}/tools/qt-faststart" -t "${pkgdir}/usr/bin"
    install -D -m644 LICENSE -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
