# Warhammer 40,000 Rogue Trader TTRPG Setting Primer

This handout is intended for use as an introductory primer for people getting into the Rogue Trader TTRPG by Fantasy Flight Games. This repo is an unlicensed fan work and is not associated with or endorsed by Games Workshop.

## Full-Bleed Printing

In order to do a full bleed duplex print, we need to print the handout centred on B4 so that we can trim it down to B4. We can do this with `pdfjam`.

Install `pdfjam` into a Nix shell:

```bash
nix-shell -p texlive.combined.scheme-full poppler_utils ghostscript
```

Then we need to centre it on B4 so that if we print it in duplex both sides will line up:

```bash
pdfjam handout.pdf \
  --papersize '{250mm,353mm}' \
  --noautoscale true \
  --scale 1 \
  --offset '0cm 0cm' \
  --outfile handout_centred_b4.pdf
```

Alternatively, for US paper sizes:

```bash
pdfjam original.pdf \
  --papersize '{11in,17in}' \
  --noautoscale true \
  --scale 1 \
  --offset '0cm 0cm' \
  --outfile handout_centred_us-tabloid.pdf
```

Remember to print with flip on long edge when printing in duplex.
