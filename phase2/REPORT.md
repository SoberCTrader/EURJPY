# EURJPY PHASE II - DATA RECEIPT & DIGEST

Run: phase2_digest.py (python 3.12.14) at 2026-11-23 10:46:27 UTC. Input dir: `/workspace/EURJPY`. Files found: 5.

## MANIFEST

| file | bytes | md5 | rows | first bar | last bar | tf | claimed | actual | symbol |
|---|---|---|---|---|---|---|---|---|---|
| CCMonthCapture EURJPY D1 20210101-20261123.csv | 74237 | 77bbde12b3865c9eed4516ed38e131ec | 1269 | 2022-01-02 22:00:00 | 2026-11-22 22:00:00 | d1 | 2021-2026 | 2022-01-02 22:00:00 .. 2026-11-22 22:00:00 | EURJPY |
| CCMonthCapture EURJPY h4 20140729-20261122.csv | 1012842 | e1a898f0bd6b54b56f2c86eae466dd48 | 17609 | 2014-07-29 01:00:00 | 2026-11-22 22:00:00 | h4 | 2014-2026 | 2014-07-29 01:00:00 .. 2026-11-22 22:00:00 | EURJPY |
| CCMonthCapture EURJPY t100 20211230-20221231.csv | 16361577 | f337a18a1337e02ee0d65cd8f642dee5 | 294595 | 2021-12-30 00:01:11 | 2022-12-30 21:56:53 | t100 | 2021-2022 | 2021-12-30 00:01:11 .. 2022-12-30 21:56:53 | EURJPY |
| CCMonthCapture EURJPY t750 20210101-20231231.csv | 5318073 | 7f80c565ef50d979748cfe8f4a56f624 | 95752 | 2021-01-03 22:01:54 | 2023-12-29 21:38:57 | t750 | 2021-2023 | 2021-01-03 22:01:54 .. 2023-12-29 21:38:57 | EURJPY |
| CCMonthCapture EURJPY t750 20240101-20261123.csv | 6565059 | 03f614c4b22994264343083ac1e6b532 | 118178 | 2024-01-01 22:17:13 | 2026-11-23 10:14:25 | t750 | 2024-2026 | 2024-01-01 22:17:13 .. 2026-11-23 10:14:25 | EURJPY |

- **d1**: 1269 rows (1 file), 2022-01-02 22:00:00 .. 2026-11-22 22:00:00; overlap 0/0 identical, 0 conflicts.
- **h4**: 17609 rows (1 file), 2014-07-29 01:00:00 .. 2026-11-22 22:00:00; overlap 0/0 identical, 0 conflicts.
- **t100**: 294595 rows (1 file), 2021-12-30 00:01:11 .. 2022-12-30 21:56:53; overlap 0/0 identical, 0 conflicts.
- **t750**: 213930 rows (2 files), 2021-01-03 22:01:54 .. 2026-11-23 10:14:25; overlap 0/0 identical, 0 conflicts.
- **UNDER-DELIVERY vs filename**: CCMonthCapture EURJPY D1 20210101-20261123.csv claims 2021-2026 but actual coverage starts 2022-01-02 (head missing 1+ years).

## FORMAT

- CCMonthCapture EURJPY D1 20210101-20261123.csv: 7 fields date,time,O,H,L,C,V confirmed
- CCMonthCapture EURJPY h4 20140729-20261122.csv: 7 fields date,time,O,H,L,C,V confirmed
- CCMonthCapture EURJPY t100 20211230-20221231.csv: 7 fields date,time,O,H,L,C,V confirmed
- CCMonthCapture EURJPY t750 20210101-20231231.csv: 7 fields date,time,O,H,L,C,V confirmed
- CCMonthCapture EURJPY t750 20240101-20261123.csv: 7 fields date,time,O,H,L,C,V confirmed

## INTEGRITY

- **d1**: wrong-field-count 0; OHLC violations 0; duplicate ts 0; non-monotonic 0; zero-range 0; zero-volume 0.
- **h4**: wrong-field-count 0; OHLC violations 0; duplicate ts 0; non-monotonic 0; zero-range 1; zero-volume 0.
- **t100**: wrong-field-count 0; OHLC violations 0; duplicate ts 0; non-monotonic 0; zero-range 0; zero-volume 0.
- **t750**: wrong-field-count 0; OHLC violations 0; duplicate ts 0; non-monotonic 0; zero-range 0; zero-volume 0.

## GAPS & SEAMS

Timezone evidence (finest timeframe t100): UTC: session-open days (first bar after a >6h gap) start at 21:00-23:59 in 100% of cases; the 21/22 split flips with US DST (EDT/EST), matching the 21:00/22:00 UTC session boundary (histogram in receipt.json).
- d1 (thr 60.0h): weekend 252, holiday 3, UNEXPLAINED 0.
- h4 (thr 10.0h): weekend 590, holiday 11, UNEXPLAINED 1.
- t100 (thr 6.0h): weekend 52, holiday 0, UNEXPLAINED 0.
- t750 (thr 6.0h): weekend 307, holiday 4, UNEXPLAINED 0.
  - UNEXPLAINED 2020-12-31 18:00:00 -> 2022-01-02 22:00:00 (8812.0h)
- holiday gaps by name: Christmas x10; New Year's Day x8
- hole map **d1**: 254 zero-bar days (incl. 247 Fridays - this timeframe has no Friday bars in part of its range): 2022-01-07, 2022-01-14 ... (full map in receipt.json)
- hole map **h4**: 308 zero-bar days (incl. 48 Fridays - this timeframe has no Friday bars in part of its range): 2017-01-01, 2017-12-24 ... (full map in receipt.json)
- hole map **t100**: 1 zero-bar days: 2022-12-25
- hole map **t750**: 3 zero-bar days: 2022-12-25, 2023-12-24 ... (full map in receipt.json)
- weekend seams: 947 total across timeframes, mean |drift| 0.09%, worst 5:
  - [h4] 2017-04-21 17:00:00 -> 2017-04-23 21:00:00 close 117.077 reopen 120.527 drift +3.450 (2.95%)
  - [h4] 2015-06-26 17:00:00 -> 2015-06-28 21:00:00 close 138.312 reopen 134.996 drift -3.316 (-2.40%)
  - [h4] 2015-07-03 17:00:00 -> 2015-07-05 21:00:00 close 136.409 reopen 134.051 drift -2.358 (-1.73%)
  - [h4] 2025-04-04 17:00:00 -> 2025-04-06 21:00:00 close 161.029 reopen 158.417 drift -2.612 (-1.62%)
  - [h4] 2022-02-25 18:00:00 -> 2022-02-27 22:00:00 close 130.235 reopen 128.429 drift -1.806 (-1.39%)

## BAD TICKS

- **d1**: 39 flagged bars (delta_close x29; wick x18; C x4). Full rows in anomalies.csv.
- **h4**: 33 flagged bars (delta_close x22; wick x16; C x6). Full rows in anomalies.csv.
- **t100**: 0 flagged bars (). Full rows in anomalies.csv.
- **t750**: 3 flagged bars (delta_close x2; H x1). Full rows in anomalies.csv.

## CROSS-VALIDATION

- same-timeframe overlaps: no same-timeframe overlaps (one file per timeframe)
- daily H/L t100 vs d1, printed-day: 259 days, H match 12 (4.6%), L match 12 (4.6%)
- daily H/L t100 vs d1, session-day: 259 days, H match 240 (92.7%), L match 199 (76.8%)
- daily H/L t100 vs h4, printed-day: 311 days, H match 43, L match 30
- daily H/L t100 vs h4, session-day: 259 days, H match 46, L match 30
- daily H/L h4 vs d1, session-day: 1268 days, H match 822 (64.8%), L match 730 (57.6%) - h4 grid is offset from the d1 day stamp, both readings reported

## CALIBRATION DIGEST

(per-year tables shown for 2021+; full history incl. pre-2021 in receipt.json. Cost tiers for EURJPY: base 0.0070, stress 0.0100 per unit = 0.700/1.000 pips, as % of avg bar range.)

### d1 (reference bars/day ~n/a; ref ticks/day ~104000)

- d1: cross-validation/synthetic frame; per-year table and 2021+ stats in receipt.json.

### h4 (reference bars/day ~n/a; ref ticks/day ~104000)

- h4: cross-validation/synthetic frame; per-year table and 2021+ stats in receipt.json.

### t100 (reference bars/day ~n/a; ref ticks/day ~104000)

| year | bars | days | bars/day | ticks/day | min/bar | avg rng | med rng | avg rng % | base % | stress % |
|---|---|---|---|---|---|---|---|---|---|---|
| 2021 | 824 | 2 | 412.0 | 41200.0 | 2.52 | 0.032 | 0.029 | 0.02 | 21.98 | 31.4 |
| 2022 | 293771 | 311 | 944.6 | 94460.0 | 1.0 | 0.039 | 0.035 | 0.03 | 17.74 | 25.35 |

- hourly bar density (00-24, printed hours): 00:12320 01:12721 02:10073 03:8816 04:7941 05:8964 06:12492 07:16668 08:16800 09:14729 10:13448 11:13828 12:16699 13:19617 14:20383 15:17751 16:13780 17:11406 18:11272 19:10237 20:6410 21:4597 22:6339 23:7304
- dead hours: none; top hours: 14,13,15,08,12,07
### t750 (reference bars/day ~n/a; ref ticks/day ~104000)

- t750: cross-validation/synthetic frame; per-year table and 2021+ stats in receipt.json.


## PHASE II READINESS

- t500 ABSENT: MA layer not runnable; t500 exports required.
- t100 2021-12-30..2022-12-30: entry layer READY (294595 bars), but faithful-transpose cells NOT runnable - t500 MA layer absent, t500 exports required.
- not present in this run: t300, t500. t300 would be derivable from t100 (groups of 3, phase calibrated by sweep) if t100 present; t750 from t1 ticks (groups of 750) where tick coverage exists; neither is derivable from a coarser bar file alone.
- present extra timeframes enabling cross-validation: t750, h4, d1. NOT present in this run: t300.
- No strategy backtest in this run - receipt and digest only; the strategy grid is a separate, later prompt.

## METHOD

- Tool: `phase2_digest.py` (python 3.12.14, stdlib only): `python3 phase2_digest.py <input_dir> [--instrument I --spread-base B --spread-stress S --pip P --synth-t500] [--out DIR]`; artifacts written next to the data; raw files read-only (in-memory copies).
- Parse: CSV, delimiter/header auto-detected; dates YYYY.MM.DD/YYYY-MM-DD/YYYY/MM/DD/YYYYMMDD; times HH:MM[:SS[.fff]]; bar files = 7 fields date,time,O,H,L,C,V (time,date auto-swapped); tick files = 4 fields date,time,bid,ask (ms timestamps) summarized as tick reference only. Bar timestamps are OPEN times, printed as-is; close-time = next bar open; last bar of each file open-ended.
- Symbol gate per file: median price outside the EURJPY range (>=200) => SUSPECT wrong symbol, excluded from merge, both readings reported. XAUUSD ref 2021->2026 ~1798->~4500s; GBPJPY ref ~124-220; EURJPY ~126-175.
- Merge per timeframe: dedupe by timestamp across files; overlaps compared bit-for-bit on printed OHLCV; conflicts reported with both readings (first file kept for stats, count disclosed). Integrity: field count != 7; H < max(O,C) or L > min(O,C); duplicate/non-monotonic timestamps; zero-range; zero-volume.
- Gap threshold per timeframe = max(6h, 2.5x median inter-bar gap). Class: weekend = Thu/Fri/Sat -> Sun/Mon 40-80h (intraday DST-adjusted 48-50h: 49h + Sun-Fri UTC offset, 4h EDT / 5h EST); holiday = span covers a computed US federal holiday 1998-2026 (Good Friday via computus, observance shifts, + 2025-01-09); else UNEXPLAINED (each listed). Hole map: zero-bar dates in [first,last] excl. Saturdays + listed holidays.
- Bad ticks (instrument-scaled, % of price): |dClose| > 1.5% of prev close (across_gap if gap > threshold), wick (H-L) > 2.5% of close, H or C == next session's reopen open (3dp) after such a gap (feed-contamination class). All flagged -> anomalies.csv; nothing deleted or fixed.
- Cross-validation: same-timeframe overlap equality; t500 = groups of 5 consecutive t100 (all 5 phases swept from file start, exact OHLCV + span); t300 = groups of 3; t100/t750 vs groups of 100/750 t1 ticks (mid and bid); daily H/L of finest frame vs h4/d1 under BOTH day definitions: printed date and DST-aware session day (open 22:00 UTC EDT / 23:00 UTC EST); --synth-t500 builds t500 from t100 groups of 5 phase 0, marked SYNTHETIC (on XAUUSD native t500 matched phase 3, 375380/375380 exact, so synthetic phase-0 grid is not bit-identical to the native chart).
- Digest: per-year bars/day, implied ticks/day = bars/day x tick size, median min/bar, avg/median range and % of close; cost ratio = spread / avg range (base 0.007, stress 0.01 per unit = 0.7/1.0 pips); hourly density on printed hours; Feb-Mar 2026 blowoff/crash metrics; weekend seam drift = reopen - prior close. Timezone: session-open first-bar hour histogram of finest timeframe vs the 21:00/22:00 UTC boundary (DST-shifting).
- Budget: REPORT.md hard-capped at 15 KB (long lists truncated here; full detail in receipt.json / anomalies.csv). Prices 3dp, percentages 2dp, timestamps full date+time as printed.
