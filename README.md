# LAC
The submission package of LAC (Lattice-based Cryptosystems) includes the following directories:

## 1. Supporting_Documentation

In the directory the pdf file "LAC.pdf" is contained. In "LAC.pdf" the submitted cryptosystems: LAC.CPA, LAC.CCA, LAC.KE, and LAC.AKE are detailed, including the algorithm specifications, parameter settings, implementation, analysis of the correctness, security and performance, and so on.

## 2. Reference_Implementation

In the directory the reference implementation of LAC is provided, written in C language. There are 27 files:

"**ake.c**": in the source file the functions "crypto_ake_alice_send", "crypto_ake_bob_receive", and "crypto_ake_alice_receive" are instantiated;

"**api.h**": all basic functions are declared here. Specifically, functions which name begins with "crypto_" are the wrapped functions providing Encrypt, kem, key exchange and authenticated key exchange operations. 

"**bin-lwe.h**": in the header file the functions for implementing computations related to poly-LWE with binary secrets and errors: "gen_a", "gen_psi", "poly_mul", "poly_aff" are declared;

"**bin-lwe.c**": in the source file the functions "gen_a", "gen_psi", "poly_mul", "poly_aff" are instantiated;

"**ecc.h**": in the header file the parameters of the BCH codes for different security categories are defined, and the functions for implementing the encoding and decoding of the BCH codes: "ecc_init", "ecc_free", "ecc_enc", and "ecc_dec", are declared;

"**ecc.c**": in the source file the functions "ecc_init", "ecc_free", "ecc_enc", and "ecc_dec", are instantiated;

"**encrypt.c**": in the source file the functions for implementing LAC.CPA: "crypto_encrypt_keypair", "crypto_encrypt", "crypto_encrypt_open", "kg", "kg_seed", "pke_enc", "pke_enc_seed", "pke_dec"are instantiated;

"**ke.c**": in the source file the functions "crypto_ke_alice_send", "crypto_ke_bob_receive", and "crypto_ke_alice_receive" are instantiated;

"**kem.c**": in the source file the functions for implementing LAC.CCA: "crypto_kem_keypair", "crypto_kem_enc", "crypto_kem_dec", "kem_enc_fo", "kem_enc_fo_seed", and "kem_dec_fo" are instantiated;

"**lac_param.h**": in the header file the parameters of LAC for different security categories are defined;

"**main.c**": in the source file the main function of the implementation are provided;

"**rand.h**": in the header file the functions for implementing the hash functions used in LAC: "random_bytes", "pseudo_random_bytes", "hash", and "gen_seed", are declared;

"**rand.c**": in the source file the functions for implementing the hash functions used in LAC: "random_bytes", "pseudo_random_bytes", "hash", and "gen_seed", are instantiated;

"**rng.h**": in the header file the randombytes functions providing by NIST at https://csrc.nist.gov/Projects/Post-Quantum-Cryptography/Post-Quantum-Cryptography-Standardization/Example-Files

"**rng.c**": in the source file the randombytes functions providing by NIST at https://csrc.nist.gov/Projects/Post-Quantum-Cryptography/Post-Quantum-Cryptography-Standardization/Example-Files

"**test_correctness.h**": in the header file the functions for testing the correctness of the cryptosystems in LAC: "test_pke_correctness", "test_kem_fo_correctness", "test_ke_correctness", "test_ake_correctness", "error_bit_num", and "print_bytes" are declared;

"**test_correctness.c**": in the source file the functions declared in "test_correctness.h" are instantiated;

"**test_cpucycles.h**": in the header file the functions for testing the cpu cycles of the cryptosystems in LAC and the basic blocks: "test_pke_cpucycles", "test_kem_fo_cpucycles", "test_ke_cpucycles", "test_ake_cpucycles", "test_hash_cpucycles", "test_aes_cpucycles", "test_gen_psi_cpucycles", "test_gen_a_cpucycles", and "test_poly_mul_cpucycles", are declared;

"**test_cpucycles.c**": in the source file the functions declared in "test_correctness.h" are instantiated;

"**test_speed.h**": in the header file the functions for testing the speed of the implementation of LAC: "test_poly_mul_speed", "test_pke_speed", "test_kem_fo_speed", "test_ke_speed", "test_ake_speed", are declared;

"**test_speed.c**": in the source file the functions declared in "test_speed.h" are instantiated;

"**Makefile**": the scripts for compling the implementation with gcc are provided;

"**bch.h**": in the hearder file, the functions for implementing the BCH codes: "free_bch", "encode_bch", "compute_even_syndromes", "decode_bch", are declared. It is a third-party free software authored by Ivan Djelic;

"**bch.c**": in the source file, the functions for implementing the BCH codes: "free_bch", "encode_bch", "compute_even_syndromes", "decode_bch", are instantiated. It is a third-party free software authored by Ivan Djelic.

"**bch128.h**": parameters using in bch for LAC128 security level.

"**bch192.h**": parameters using in bch for LAC192 security level.

"**bch256.h**": parameters using in bch for LAC256 security level.

Both "bch.h" and "bch.c" are obtained in https://github.com/jkent/python-bchlib/tree/master/bchlib.
Via an e-mail request, the use of "bch.h" and "bch.c" has been approved by NIST.

## 3. Optimized_Implementation

-----------------------------
In the directory the optimized implementation of LAC for the Intel x64 processor is provided, written in C language. 

There are also 27 files in the directory, and with the same names and functionalities as those in the directory "Reference_Implementation".

## 4. AVX2_Implementation

-----------------------------
In the directory the optimized implementation of LAC for the Intel x64 processor is provided, written in C language with AVX2 instructions.

There are also 27 files in the directory, and with the same names and functionalities as those in the directory "Reference_Implementation".

## 5. KAT

-----------------------------
In the directory the KAT values, and the source codes for generating them are provided. There are 4 subdirectories in the directory "KAT":
- The subdirectory "lac-ref" .
- The subdirectory "lac-opt" .
- The subdirectory "lac-avx" .

- The subdirectory "KAT_VALUES":
  There are 4 subdirectories, "ENCRYPT", "KEM", "KE", "AKE", in which the KAT values for different security categories of LAC.CPA, LAC.CCA, LAC.KE, LAC.AKE respectively.