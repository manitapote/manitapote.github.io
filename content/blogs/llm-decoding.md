# LLM Decoding Strategies

Decoding stragties are the methods that is used to choose the next token prediction in LLMs.

# Deterministic strategies
## Greedy decoding
In this method, at every step token with the highest probability is chosen.
The problem with this method is that this method choose locally optimal token but not globally optimal.
This is used when the latency matters most and tasks has fairly unambiguous correct output like code completion for syntax, simple classification style generation.

## Beam Search

# Stochastic sampling strategies
## Tok-k sampling
## Top-p (nucleus) sampling
## Min-p sampling

## Typical sampling
## Contrastive search
## Repetition/frequency penalties
## Speculative decoding
