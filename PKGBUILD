# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer : Daniel Bermond <dbermond@archlinux.org>
# Contributor: Iacopo Isimbaldi <isiachi@rhye.it>

_pkg=ffmpeg
pkgname="${_pkg}-full"
pkgver=7.1
pkgrel=1
_svt_hevc_ver='ed80959ebb5586aa7763c91a397d44be1798587c'
_svt_vp9_ver='3b9a3fa43da4cc5fe60c7d22afe2be15341392ea'
_pkgdesc=(
  'Complete solution to record,'
  'convert and stream audio and video'
  '(all possible features including libfdk-aac)'
pkgdesc="${_pkgdesc[*]}"
arch=(
  'x86_64'
  'i686'
  'pentium4'
  'arm'
  'aarch64'
  'armv7l'
  'armv6l'
  'mips'
  'powerpc'
)
url="https://www.${_pkg}.org"
license=(
  'LicenseRef-nonfree-and-unredistributable'
)
depends=(
    'alsa-lib'
    'aom'
    'aribb24'
    'avisynthplus'
    'bzip2'
    'cairo'
    'celt'
    'codec2'
    'cuda'
    'dav1d'
    'flite1'
    'fontconfig'
    'freetype2'
    'frei0r-plugins'
    'fribidi'
    'glib2'
    'glslang'
    'gmp'
    'gnutls'
    'gsm'
    'harfbuzz'
    'jack'
    'kvazaar'
    'ladspa'
    'lame'
    'lcevcdec'
    'lcms2'
    'lensfun-git'
    'libass'
    'libavc1394'
    'libbluray'
    'libbs2b'
    'libcaca'
    'libcdio-paranoia'
    'libdc1394'
    'libdrm'
    'libdvdnav'
    'libdvdread'
    'libfdk-aac'
    'libgcrypt'
    'libgl'
    'libgme'
    'libiec61883'
    'libilbc'
    'libjxl'
    'liblc3'
    'libmodplug'
    'libmysofa'
    'libomxil-bellagio'
    'libopenmpt'
    'libplacebo'
    'libpulse'
    'librabbitmq-c'
    'libraw1394'
    'librist'
    'librsvg'
    'libsoxr'
    'libssh'
    'libtheora'
    'libva'
    'libvdpau'
    'libvorbis'
    'libvpl'
    'libvpx'
    'libx11'
    'libxcb'
    'libxext'
    'libxml2'
    'libxv'
    'libwebp'
    'lilv'
    'lv2'
    'ocl-icd'
    'openal'
    'opencore-amr'
    'opencv2'
    'openh264'
    'openjpeg2'
    'openvino'
    'opus'
    'qrencode'
    'quirc'
    'rav1e'
    'rtmpdump'
    'rubberband'
    'sdl2'
    'smbclient'
    'snappy'
    'sndio'
    'speex'
    'spirv-tools'
    'srt'
    'svt-av1'
    'svt-hevc'
    'svt-vp9'
    'tesseract'
    'twolame'
    'v4l-utils'
    'vapoursynth'
    'vid.stab'
    'vmaf'
    'vulkan-icd-loader'
    'x264'
    'x265'
    'xvidcore'
    'xz'
    'zeromq'
    'zimg'
    'zlib'
    'zvbi'
    # aur:
    'chromaprint-fftw'
    'davs2'
    'libaribcaption'
    'libklvanc'
    'rockchip-mpp'
    'shine'
    'uavs3d-git'
    'vo-amrwbenc'
    'vvenc'
    'xavs'
    'xavs2'
    'xevd'
    'xeve'
)
optdepends=(
  'nvidia-utils: for NVIDIA NVDEC/NVENC support'
  'vpl-runtime: for Intel Quick Sync Video'
)
makedepends=(
  'patchutils'
  'clang'
  'nasm'
  'amf-headers'
  'ffnvcodec-headers'
  'opencl-headers'
  'vulkan-headers'
  # aur:
  'decklink-sdk'
)
provides=(
  'libavcodec.so'
  'libavdevice.so'
  'libavfilter.so'
  'libavformat.so'
  'libavutil.so'
  'libpostproc.so'
  'libswscale.so'
  'libswresample.so'
  "${_pkg}=${pkgver}"
)
conflicts=(
  "${_pkg}"
)
_gh_raw="https://raw.githubusercontent.com"
_ovc_ns="OpenVisualCloud"
_svt_hevc_raw="${_gh_raw}/${_ovc_ns}/SVT-HEVC"
_svt_hevc_pkg_plugin="${_svt_hevc_raw}/${_svt_hevc_ver}/${_pkg}_plugin"
_svt_vp9_raw="${_gh_raw}/${_ovc_ns}/SVT-VP9"
_svt_vp9_pkg_plugin="${_svt_vp9_raw}/${_svt_vp9_ver}/${_pkg}_plugin"
_svt_hevc_ver_patch="010-${_pkg}-add-svt-hevc-g${_svt_hevc_ver:0:7}.patch"
_svt_hevc_ver_patch_url="${_svt_hevc_pkg_plugin}/master-0001-lavc-svt_hevc-add-libsvt-hevc-encoder-wrapper.patch"
_svt_hevc_docs_ver_patch="020-${_pkg}-add-svt-hevc-docs-g${_svt_hevc_ver:0:7}.patch"
_svt_hevc_docs_ver_patch_url="${_svt_hevc_pkg_plugin}/0002-doc-Add-libsvt_hevc-encoder-docs.patch"
_svt_vp9_ver_patch="030-${_pkg}-add-svt-vp9-g${_svt_vp9_ver:0:7}.patch"
_svt_vp9_ver_patch_url="${_svt_vp9_pkg_plugin}/master-0001-Add-ability-for-${_pkg}-to-run-svt-vp9.patch"
_svt_vp9_patch="031-${_pkg}-add-svt-vp9.patch"
_chromium_patch="040-${_pkg}-add-av_stream_get_first_dts-for-chromium.patch"
_avisynthplus_patch="050-${_pkg}-fix-segfault-with-avisynthplus.patch"
_nvidia_patch="060-${_pkg}-fix-nvidia-vulkan-decoding-segfault.patch"
_patches=(
  "${_svt_hevc_ver_patch}"
  "${_svt_hevc_docs_ver_patch}"
  "${_svt_vp9_ver_patch}"
  "${_svt_vp9_patch}"
  "${_chromium_patch}"
  "${_avisynthplus_patch}"
  "${_nvidia_patch}"
)
source=(
  "${url}/releases/${_pkg}-${pkgver}.tar.xz"{,.asc}
  "${_svt_hevc_ver_patch}::${_svt_hevc_ver_patch_url}"
  "${_svt_hevc_docs_ver_patch}::${_svt_hevc_docs_ver_patch_url}"
  "${_svt_vp9_ver_patch}::${_svt_vp9_ver_patch_url}"
  "${_svt_vp9_patch}"
  "${_chromium_patch}"
  "${_avisynthplus_patch}"
  "${_nvidia_patch}"
  'LICENSE'
)
sha256sums=(
  '40973d44970dbc83ef302b0609f2e74982be2d85916dd2ee7472d30678a7abe6'
  'SKIP'
  '9047e18d34716812d4ea7eafc1d0fd8b376d922a4b6b4dc20237662fcaf0c996'
  'a164ebdc4d281352bf7ad1b179aae4aeb33f1191c444bed96cb8ab333c046f81'
  '59da61f2b2c556fbe0cdbf84bcc00977ee3d2447085decb21f6298226559f2aa'
  'aa0daffc4d234b6621b63c298dc165d29522c5087f8905a923d23ee2d164e9ad'
  '57697441b8f3ff3be883a2444b4cb89eed452764d24965e74e7b101e6af7f70a'
  '26419f819d1f3e4d0534995b73d05a8195bc7c892b74c37c3880085af027515b'
  '5a3731d1410747703948c87e46bb3aef820c6038f7101ab37f9d072cd1d15d15'
  '04a7176400907fd7db0d69116b99de49e582a6e176b3bfb36a03e50a4cb26a36'
)
validpgpkeys=(
  'FCF986EA15E6E293A5644F10B4322F04D67658D8'
)

prepare() {
  local \
    _patch
  rm \
    -f \
    "${_pkg}-${pkgver}/libavcodec/libsvt_"{"hevc","vp9"}.c
  for _patch in "${_patches[@]}"; do
    patch \
      -d \
        "${_pkg}-${pkgver}" \
      -Np1 \
      -i \
      "${srcdir}/${_patch}"
  done
}

build() {
  local \
    _configure_opts=()
  cd \
    "${_pkg}-${pkgver}"
  printf \
    '%s\n' \
    '  -> Running ffmpeg configure script...'
  export \
    CFLAGS+=' -isystem/opt/cuda/include'
  export \
    LDFLAGS+=' -L/opt/cuda/lib64'
  export \
    PKG_CONFIG_PATH="/opt/intel/openvino/runtime/lib/intel64/pkgconfig${PKG_CONFIG_PATH:+":${PKG_CONFIG_PATH}"}"
  # fix build of libavfilter/asrc_flite.c with gcc 14
  export \
    CFLAGS+=' -Wno-incompatible-pointer-types'
  _configure_opts+=(
    --prefix='/usr'
    --enable-lto

    --disable-rpath
    --enable-gpl
    --enable-version3
    --enable-nonfree
    --enable-shared
    --disable-static
    --disable-stripping
    --disable-htmlpages
    --enable-gray

    --enable-alsa
    --enable-avisynth
    --enable-bzlib
    --enable-chromaprint
    --enable-frei0r
    --enable-gcrypt
    --enable-gmp
    --enable-gnutls
    --enable-iconv
    --enable-ladspa
    --enable-lcms2
    --enable-libaom
    --enable-libaribb24
    --enable-libaribcaption
    --enable-libass
    --enable-libbluray
    --enable-libbs2b
    --enable-libcaca
    --enable-libcelt
    --enable-libcdio
    --enable-libcodec2
    --enable-libdav1d
    --enable-libdavs2
    --enable-libdc1394
    --enable-libdvdnav
    --enable-libdvdread
    --enable-libfdk-aac
    --enable-libflite
    --enable-libfontconfig
    --enable-libfreetype
    --enable-libfribidi
    --enable-libharfbuzz
    --enable-libglslang
    --enable-libgme
    --enable-libgsm
    --enable-libiec61883
    --enable-libilbc
    --enable-libjack
    --enable-libjxl
    --enable-libklvanc
    --enable-libkvazaar
    --enable-liblc3
    --enable-liblcevc-dec
    --enable-liblensfun
    --enable-libmodplug
    --enable-libmp3lame
    --enable-libopencore-amrnb
    --enable-libopencore-amrwb
    --enable-libopencv
    --enable-libopenh264
    --enable-libopenjpeg
    --enable-libopenmpt
    --enable-libopenvino
    --enable-libopus
    --enable-libplacebo
    --enable-libpulse
    --enable-libqrencode
    --enable-libquirc
    --enable-librabbitmq
    --enable-librav1e
    --enable-librist
    --enable-librsvg
    --enable-librubberband
    --enable-librtmp
    --disable-libshaderc
    --enable-libshine
    --enable-libsmbclient
    --enable-libsnappy
    --enable-libsoxr
    --enable-libspeex
    --enable-libsrt
    --enable-libssh
    --enable-libsvtav1
    --enable-libsvthevc
    --enable-libsvtvp9
    --disable-libtensorflow
    --enable-libtesseract
    --enable-libtheora
    --disable-libtls
    --disable-libtorch
    --enable-libtwolame
    --enable-libuavs3d
    --enable-libv4l2
    --enable-libvidstab
    --enable-libvmaf
    --enable-libvo-amrwbenc
    --enable-libvorbis
    --enable-libvpx
    --enable-libvvenc
    --enable-libwebp
    --enable-libx264
    --enable-libx265
    --enable-libxevd
    --enable-libxeve
    --enable-libxavs
    --enable-libxavs2
    --enable-libxcb
    --enable-libxcb-shm
    --enable-libxcb-xfixes
    --enable-libxcb-shape
    --enable-libxvid
    --enable-libxml2
    --enable-libzimg
    --enable-libzmq
    --enable-libzvbi
    --enable-lv2
    --enable-lzma
    --enable-decklink
    --disable-mbedtls
    --enable-libmysofa
    --enable-openal
    --enable-opencl
    --enable-opengl
    --disable-openssl
    --disable-pocketsphinx
    --enable-sndio
    --enable-sdl2
    --enable-vapoursynth
    --enable-vulkan
    --enable-xlib
    --enable-zlib

    --enable-amf 
    --enable-cuda-nvcc
    --enable-cuda-llvm
    --enable-cuvid
    --enable-ffnvcodec
    --enable-libdrm
    --enable-libvpl
    --enable-libnpp
    --enable-nvdec
    --enable-nvenc
    --enable-omx
    --enable-rkmpp
    --enable-v4l2-m2m
    --enable-vaapi
    --enable-vdpau
  )
  ./configure \
    "${_configure_opts[@]}"
  make
  make \
    tools/qt-faststart
}

package() {
  make \
    -C \
      "${_pkg}-${pkgver}" \
    DESTDIR="$pkgdir" \
    install
  install \
    -Dm755 \
    "${_pkg}-${pkgver}/tools/qt-faststart" \
    -t \
    "${pkgdir}/usr/bin"
  install \
    -Dm644 \
    "LICENSE" \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}"
}
