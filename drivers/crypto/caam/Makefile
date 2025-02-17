# SPDX-License-Identifier: GPL-2.0
#
# Makefile for the CAAM backend and dependent components
#
ifeq ($(CONFIG_CRYPTO_DEV_FSL_CAAM_DEBUG), y)
	ccflags-y := -DDEBUG
endif

ccflags-y += -DVERSION=\"\"

obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_COMMON) += error.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM) += caam.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_JR) += caam_jr.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_CRYPTO_API_DESC) += caamalg_desc.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_AHASH_API_DESC) += caamhash_desc.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_KEYBLOB_API_DESC) += caamkeyblob_desc.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_JR_UIO) += fsl_jr_uio.o

caam-y := ctrl.o
caam_jr-y := jr.o key_gen.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_TK_API) += tag_object.o caamkeyblob.o caamkeygen.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_CRYPTO_API) += caamalg.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_CRYPTO_API_QI) += caamalg_qi.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_AHASH_API) += caamhash.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_RNG_API) += caamrng.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_PKC_API) += caampkc.o pkc_desc.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_BLOB_GEN) += blob_gen.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_SM) += sm_store.o
caam_jr-$(CONFIG_CRYPTO_DEV_FSL_CAAM_PRNG_API) += caamprng.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_SM_TEST) += sm_test.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_SECVIO) += secvio.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_TK_API_TEST) += caamkeyblob_test.o

caam-$(CONFIG_CRYPTO_DEV_FSL_CAAM_CRYPTO_API_QI) += qi.o
ifneq ($(CONFIG_CRYPTO_DEV_FSL_CAAM_CRYPTO_API_QI),)
	ccflags-y += -DCONFIG_CAAM_QI
endif

caam-$(CONFIG_DEBUG_FS) += debugfs.o

obj-$(CONFIG_CRYPTO_DEV_FSL_DPAA2_CAAM) += dpaa2_caam.o
obj-$(CONFIG_CRYPTO_DEV_FSL_CAAM_KEYBLOB) += caam_keyblob.o

dpaa2_caam-y    := caamalg_qi2.o dpseci.o
dpaa2_caam-$(CONFIG_DEBUG_FS) += dpseci-debugfs.o
