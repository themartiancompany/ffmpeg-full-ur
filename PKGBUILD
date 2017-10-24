# Maintainer : Daniel Bermond < yahoo-com: danielbermond >
# Contributor: Iacopo Isimbaldi <isiachi@rhye.it>

# NOTE:
# To enable NewTek NDI (libndi), install the package 'ndi-sdk'
# and add '--enable-libndi_newtek' to the configure options.

pkgname=ffmpeg-full
_srcname=ffmpeg
pkgver=3.4
pkgrel=2
pkgdesc='Record, convert and stream audio and video (all possible features including nvenc, qsv and libfdk-aac)'
arch=('i686' 'x86_64')
url='http://www.ffmpeg.org/'
license=('custom: nonfree and unredistributable')
depends=(
    # official repositories:
        'glibc' 'alsa-lib' 'jack' 'libpng'
        'bzip2' 'frei0r-plugins' 'libgcrypt' 'gmp' 'gnutls' 'ladspa' 'libass'
        'libbluray' 'libcaca' 'celt' 'libcdio-paranoia' 'libdc1394' 'libavc1394'
        'libfdk-aac' 'fontconfig' 'freetype2' 'fribidi' 'libgme' 'gsm' 'libiec61883'
        'libmodplug' 'lame' 'opencore-amr' 'opencv' 'openjpeg2' 'opus' 'pulseaudio'
        'librsvg' 'rubberband' 'rtmpdump' 'smbclient' 'snappy' 'libsoxr' 'speex'
        'libssh' 'tesseract' 'libtheora' 'twolame' 'v4l-utils' 'vid.stab' 'libvorbis'
        'libvpx' 'wavpack' 'libwebp' 'libx264.so' 'x265' 'libxcb' 'xvidcore' 'libxml2'
        'zimg' 'zeromq' 'zvbi' 'xz' 'openal' 'opencl-icd-loader' 'mesa' 'openssl'
        'sdl2' 'libx11' 'zlib' 'libomxil-bellagio' 'libva' 'libdrm' 'libvdpau'
    # AUR:
        'chromaprint-fftw' 'libbs2b' 'flite1' 'libilbc' 'kvazaar' 'openh264'
        'libopenmpt-svn' 'sndio' 'shine' 'vo-amrwbenc' 'xavs' 'libmysofa' 'rockchip-mpp'
)
depends_x86_64=('cuda' 'nvidia-utils')
optdepends_x86_64=(
    # AUR:
        'intel-media-sdk: for Intel QSV support (experimental)'
)
makedepends=(
    # official repositories:
        'nasm' 'opencl-headers'
    # AUR:
        'blackmagic-decklink-sdk' 'libmfx' 'libvmaf'
)
provides=(
    'ffmpeg' 'ffmpeg-full-nvenc' 'ffmpeg-nvenc' 'ffmpeg-libfdk_aac' 'ffmpeg-decklink'
    'qt-faststart' 'libavutil.so' 'libavcodec.so' 'libavformat.so' 'libavdevice.so'
    'libavfilter.so' 'libavresample.so' 'libswscale.so' 'libswresample.so'
    'libpostproc.so'
)
conflicts=(
    'ffmpeg' 'ffmpeg-full-nvenc' 'ffmpeg-nvenc' 'ffmpeg-libfdk_aac' 'ffmpeg-decklink'
    'ffmpeg-git' 'ffmpeg-full-git' 'ffmpeg-semifull-git' 'ffmpeg-qsv-git'
)
source=("https://ffmpeg.org/releases/ffmpeg-${pkgver}.tar.xz"
        'LICENSE')
sha256sums=('aeee06e4d8b18d852c61ebbfe5e1bb7014b1e118e8728c1c2115f91e51bffbef'
            '04a7176400907fd7db0d69116b99de49e582a6e176b3bfb36a03e50a4cb26a36')

build() {
    cd "${_srcname}-${pkgver}"
    
    # set x86_64 specific options
    if [ "$CARCH" = 'x86_64' ] 
    then
        local _cuda='--enable-cuda'
        local _cudasdk='--enable-cuda-sdk'
        local _cuvid='--enable-cuvid'
        local _libnpp='--enable-libnpp'
        local _cflags='--extra-cflags=-I/opt/cuda/include'
        
        # '-L/usr/lib/nvidia' (for cuda_sdk) needs to be enabled only on
        # systems with nvidia-340xx-utils or nvidia-304xx-utils
        if pacman -Qqs '^nvidia-340xx-utils$' | grep -q '^nvidia-340xx-utils$' ||
           pacman -Qqs '^nvidia-304xx-utils$' | grep -q '^nvidia-304xx-utils$'
        then
            local _nvidia_340xx_ldflags='-L/usr/lib/nvidia'
        fi
        local _ldflags="--extra-ldflags=-L/opt/cuda/lib64 ${_nvidia_340xx_ldflags}"
        local _ldflags="${_ldflags} -Wl,-rpath -Wl,/opt/intel/mediasdk/lib64:/opt/intel/mediasdk/plugins"
        
        # strictly specifying nvcc path is needed if package is installing
        # cuda for the first time (nvcc path will be in $PATH only after relogin)
        sed -i "s@^nvcc_default=.*@nvcc_default='/opt/cuda/bin/nvcc'@" configure
    fi
    
    msg2 'Running ffmpeg configure script. Please wait...'
    
    ./configure \
        --prefix='/usr' \
        $_cflags \
        "$_ldflags" \
        \
        --enable-rpath \
        --enable-gpl \
        --enable-version3 \
        --enable-nonfree \
        --enable-shared \
        --disable-static \
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
        --enable-jack \
        --enable-ladspa \
        --enable-libass \
        --enable-libbluray \
        --enable-libbs2b \
        --enable-libcaca \
        --enable-libcelt \
        --enable-libcdio \
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
        --enable-libkvazaar \
        --enable-libmodplug \
        --enable-libmp3lame \
        --enable-libopencore-amrnb \
        --enable-libopencore-amrwb \
        --enable-libopencv \
        --enable-libopenh264 \
        --enable-libopenjpeg \
        --enable-libopenmpt \
        --enable-libopus \
        --enable-libpulse \
        --enable-librsvg \
        --enable-librubberband \
        --enable-librtmp  \
        --enable-libshine \
        --enable-libsmbclient \
        --enable-libsnappy \
        --enable-libsoxr \
        --enable-libspeex \
        --enable-libssh \
        --enable-libtesseract \
        --enable-libtheora \
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
        --enable-libxcb \
        --enable-libxcb-shm \
        --enable-libxcb-xfixes \
        --enable-libxcb-shape \
        --enable-libxvid \
        --enable-libxml2 \
        --enable-libzimg \
        --enable-libzmq \
        --enable-libzvbi \
        --enable-lzma \
        --enable-decklink \
        --enable-libmysofa \
        --enable-openal \
        --enable-opencl \
        --enable-opengl \
        --enable-openssl \
        --enable-sndio \
        --enable-sdl2 \
        --enable-xlib \
        --enable-zlib \
        \
        $_cuda \
        $_cudasdk \
        $_cuvid \
        --enable-libdrm \
        --enable-libmfx \
        $_libnpp \
        --enable-nvenc \
        --enable-omx \
        --enable-omx-rpi \
        --enable-rkmpp \
        --enable-vaapi \
        --enable-vdpau
    make
    make tools/qt-faststart
}

package() {
    cd "${_srcname}-${pkgver}"
    make DESTDIR="$pkgdir" install
    
    install -D -m755 tools/qt-faststart  "${pkgdir}/usr/bin/qt-faststart"
    install -D -m644 "${srcdir}/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
