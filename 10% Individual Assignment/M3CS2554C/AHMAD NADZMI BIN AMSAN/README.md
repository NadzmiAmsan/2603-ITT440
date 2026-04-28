# 🔓 Parallel Hash Breaker: Cracking Passwords at the Speed of Parallel Computing

Name: Ahmad Nadzmi Bin Amsan 

Student ID: 2025239524

Course Code: ITT440: Network Programming

Lecturer: Shahadan Bin Saad

Youtube Link : https://www.youtube.com/watch?v=EzCX8cD6PAc&t=6s

# 🎯 Mission Objective
In password security auditing, time is the only barrier between a hash and its plaintext. Traditional brute‑force methods test one password at a time, making complex cracking attempts painfully slow. The Parallel Hash Breaker is a high‑performance cryptographic cracker that leverages multiprocessing, threading, and sequential models to demonstrate real‑world parallel computing concepts.

# 📁 Project Overview
The Parallel Hash Breaker is a Python‑based tool designed to teach and demonstrate the differences between sequential, threaded, and parallel (multiprocessing) execution for CPU‑bound tasks.

# 💻 Hardware & Environment
Processor: Quad‑Core / Octa‑Core CPU (e.g., Intel i5‑8250U @ 1.60GHz)

Memory: 8GB RAM minimum

OS: Linux Environment (Ubuntu 22.04+ recommended)

Runtime: Python 3.8+ with matplotlib for analytics and tqdm for real‑time progress bars.

# 🛠️ Install required libraries
The Parallel Hash Breaker uses two optional but highly recommended libraries:

1. matplotlib – Automatic Graph Generation
Purpose: After each benchmark run, the script automatically generates professional‑grade graphs.

2. tqdm – Real‑time Progress Bars
Purpose: Shows a live, updating progress bar during the sequential crack, giving visual feedback on how many passwords have been tested and the estimated time remaining.

# 🔋Run the full benchmark
python parallel_hash_breaker.py --limit 50000000

# 📊 Battlefield Analytics
**A. Single Large Task** (50 Million Hashes) – Default SHA256
When cracking a SHA‑256 hash positioned near the end of a 50‑million number space:

Method	Time (seconds)	Speedup vs Sequential
Sequential (1 core)	36.14 s	1.00x (baseline)
Threading (8 threads)	35.92 s	1.01x (GIL limited)
Parallel (8 cores)	11.34 s	3.19x 🚀

**B. Effect of Hash Algorithm** – MD5 vs SHA256
Algorithm	Sequential Time (s)	Parallel Time (8 cores)	Speedup
SHA256	36.14	11.34	3.19x
MD5	28.50	8.90	3.20x

**C. Scaling with Fewer Workers** – The --workers 2 Test
Workers	Time (s)	Speedup vs Sequential
1 (sequential)	36.14	1.00x
2	18.92	1.91x
4	14.10	2.56x
8	11.34	3.19x

**D. Dictionary Attack** – Fast Wordlist Cracking
The dictionary attack tries common words plus simple mutations for extremely fast cracking.

**E. Lightweight Difficulty Benchmark**
Level	Passwords	Algorithm	Speedup
very_easy	100,000	md5	2.53x
easy	10,000	md5	2.25x
intermediate	1,000	sha256	2.50x
hard	100	sha256	2.00x
very_hard	10	sha512	1.00x

# 🧠 How It Works
The Parallel Hash Breaker implements three distinct cracking models:

1. Sequential (Baseline) - Single core hashes each number one by one.
2. Threading (GIL Demonstration) - Threads run concurrently but limited by the Global Interpreter Lock.
3. Parallel (Multiprocessing) – True Speedup with each core running a separate Python process.
4. Difficulty Benchmark - Lightweight and fast for demonstrations.

# ✅ Conclusion
The Parallel Hash Breaker successfully demonstrates true parallelism, threading limitations, and practical speedups of 3x or more on a standard laptop.