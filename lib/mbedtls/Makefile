# SPDX-License-Identifier: GPL-2.0+
#
# Copyright (c) 2024 Linaro Limited
# Author: Raymond Mao <raymond.mao@linaro.org>

MBEDTLS_LIB_DIR = external/mbedtls/library

# shim layer for hash
obj-$(CONFIG_$(SPL_)MD5_MBEDTLS) += md5.o
obj-$(CONFIG_$(SPL_)SHA1_MBEDTLS) += sha1.o
obj-$(CONFIG_$(SPL_)SHA256_MBEDTLS) += sha256.o
obj-$(CONFIG_$(SPL_)SHA512_MBEDTLS) += sha512.o

# x509 libraries
obj-$(CONFIG_$(SPL_)ASYMMETRIC_PUBLIC_KEY_MBEDTLS) += \
	public_key.o
obj-$(CONFIG_$(SPL_)X509_CERTIFICATE_PARSER_MBEDTLS) += \
	x509_cert_parser.o
obj-$(CONFIG_$(SPL_)PKCS7_MESSAGE_PARSER_MBEDTLS) += pkcs7_parser.o
obj-$(CONFIG_$(SPL_)MSCODE_PARSER_MBEDTLS) += mscode_parser.o
obj-$(CONFIG_$(SPL_)RSA_PUBLIC_KEY_PARSER_MBEDTLS) += rsa_helper.o

# MbedTLS crypto library
obj-$(CONFIG_MBEDTLS_LIB) += mbedtls_lib_crypto.o
mbedtls_lib_crypto-y := \
	$(MBEDTLS_LIB_DIR)/platform_util.o \
	$(MBEDTLS_LIB_DIR)/constant_time.o \
	$(MBEDTLS_LIB_DIR)/md.o

mbedtls_lib_crypto-$(CONFIG_$(SPL_)MD5_MBEDTLS) += $(MBEDTLS_LIB_DIR)/md5.o
mbedtls_lib_crypto-$(CONFIG_$(SPL_)SHA1_MBEDTLS) += $(MBEDTLS_LIB_DIR)/sha1.o
mbedtls_lib_crypto-$(CONFIG_$(SPL_)SHA256_MBEDTLS) += \
	$(MBEDTLS_LIB_DIR)/sha256.o
mbedtls_lib_crypto-$(CONFIG_$(SPL_)SHA512_MBEDTLS) += \
	$(MBEDTLS_LIB_DIR)/sha512.o

# MbedTLS X509 library
obj-$(CONFIG_MBEDTLS_LIB_X509) += mbedtls_lib_x509.o
mbedtls_lib_x509-y := $(MBEDTLS_LIB_DIR)/x509.o
mbedtls_lib_x509-$(CONFIG_$(SPL_)ASN1_DECODER_MBEDTLS) += \
	$(MBEDTLS_LIB_DIR)/asn1parse.o \
	$(MBEDTLS_LIB_DIR)/asn1write.o \
	$(MBEDTLS_LIB_DIR)/oid.o
mbedtls_lib_x509-$(CONFIG_$(SPL_)RSA_PUBLIC_KEY_PARSER_MBEDTLS) += \
	$(MBEDTLS_LIB_DIR)/bignum.o \
	$(MBEDTLS_LIB_DIR)/bignum_core.o \
	$(MBEDTLS_LIB_DIR)/rsa.o \
	$(MBEDTLS_LIB_DIR)/rsa_alt_helpers.o
mbedtls_lib_x509-$(CONFIG_$(SPL_)ASYMMETRIC_PUBLIC_KEY_MBEDTLS) += \
	$(MBEDTLS_LIB_DIR)/pk.o \
	$(MBEDTLS_LIB_DIR)/pk_wrap.o \
	$(MBEDTLS_LIB_DIR)/pkparse.o
mbedtls_lib_x509-$(CONFIG_$(SPL_)X509_CERTIFICATE_PARSER_MBEDTLS) += \
	$(MBEDTLS_LIB_DIR)/x509_crl.o \
	$(MBEDTLS_LIB_DIR)/x509_crt.o
mbedtls_lib_x509-$(CONFIG_$(SPL_)PKCS7_MESSAGE_PARSER_MBEDTLS) += \
	$(MBEDTLS_LIB_DIR)/pkcs7.o

#mbedTLS TLS support
obj-$(CONFIG_MBEDTLS_LIB_TLS) += mbedtls_lib_tls.o
mbedtls_lib_tls-y := \
	$(MBEDTLS_LIB_DIR)/mps_reader.o \
	$(MBEDTLS_LIB_DIR)/mps_trace.o \
	$(MBEDTLS_LIB_DIR)/net_sockets.o \
	$(MBEDTLS_LIB_DIR)/pk_ecc.o \
	$(MBEDTLS_LIB_DIR)/ssl_cache.o \
	$(MBEDTLS_LIB_DIR)/ssl_ciphersuites.o \
	$(MBEDTLS_LIB_DIR)/ssl_client.o \
	$(MBEDTLS_LIB_DIR)/ssl_cookie.o \
	$(MBEDTLS_LIB_DIR)/ssl_debug_helpers_generated.o \
	$(MBEDTLS_LIB_DIR)/ssl_msg.o \
	$(MBEDTLS_LIB_DIR)/ssl_ticket.o \
	$(MBEDTLS_LIB_DIR)/ssl_tls.o \
	$(MBEDTLS_LIB_DIR)/ssl_tls12_client.o \
	$(MBEDTLS_LIB_DIR)/hmac_drbg.o \
	$(MBEDTLS_LIB_DIR)/ctr_drbg.o \
	$(MBEDTLS_LIB_DIR)/entropy.o \
	$(MBEDTLS_LIB_DIR)/entropy_poll.o \
	$(MBEDTLS_LIB_DIR)/aes.o \
	$(MBEDTLS_LIB_DIR)/cipher.o \
	$(MBEDTLS_LIB_DIR)/cipher_wrap.o \
	$(MBEDTLS_LIB_DIR)/ecdh.o \
	$(MBEDTLS_LIB_DIR)/ecdsa.o \
	$(MBEDTLS_LIB_DIR)/ecp.o \
	$(MBEDTLS_LIB_DIR)/ecp_curves.o \
	$(MBEDTLS_LIB_DIR)/ecp_curves_new.o \
	$(MBEDTLS_LIB_DIR)/gcm.o \
