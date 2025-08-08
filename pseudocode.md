# Lilith pseudocode (minimal)

init θ; Opt = Adam(θ, lr)
best_val = +∞; plateau = 0
set PATIENCE, MASK_RATE, SIGMA, COOLDOWN, TOL
cool = 0

for each epoch:
  train one epoch with Opt
  val = evaluate()

  if best_val - val > TOL:
    best_val = val; plateau = 0
  else:
    plateau += 1

  if plateau >= PATIENCE and cool == 0:
    backup = copy(θ)
    for each tensor θi:
      Mi = BernoulliMask(prob=MASK_RATE)
      ηi = Normal(0, SIGMA)
      θi ← θi + Mi ⊙ ηi
    cool = COOLDOWN
    val_after = quick_eval()
    if val_after > val + TOL:
      θ ← backup            # rollback
      SIGMA ← 0.5*SIGMA; MASK_RATE ← 0.5*MASK_RATE
    plateau = 0
  else if cool > 0:
    cool -= 1
