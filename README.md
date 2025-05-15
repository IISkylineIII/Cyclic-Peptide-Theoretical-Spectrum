# Cyclic-Peptide-Theoretical-Spectrum


# Description
This Python script calculates the theoretical mass spectrum of a cyclic peptide. It generates all cyclic subpeptides, computes their masses based on amino acid masses, and returns a sorted spectrum including zero mass and the entire peptide mass.

# Usage

Example 
```

def calculate_mass(peptide):
    mass_table = {
        'A': 71, 'C': 103, 'D': 115, 'E': 129, 'F': 147,
        'G': 57, 'H': 137, 'I': 113, 'K': 128, 'L': 113,
        'M': 131, 'N': 114, 'P': 97, 'Q': 128, 'R': 156,
        'S': 87, 'T': 101, 'V': 99, 'W': 186, 'Y': 163
    }
    return sum([mass_table[aa] for aa in peptide])

def cyclic_subpeptides(peptide):
    cyclic_peptide = peptide + peptide
    subpeptides = [cyclic_peptide[i:i + len(peptide)] for i in range(len(peptide))]
    subpeptides.append(peptide)  # Add entire cyclic peptide
    return subpeptides

def theoretical_spectrum(peptide):
    subpeptides = cyclic_subpeptides(peptide)
    spectrum = [0]

    for subpeptide in subpeptides:
        mass = calculate_mass(subpeptide)
        spectrum.append(mass)

    return sorted(spectrum)

# Example usage
peptide = "LEQN"
spectrum = theoretical_spectrum(peptide)
print(" ".join(map(str, spectrum)))

```

# Output


# Function Descriptions
* calculate_mass(peptide): Returns the total mass of the peptide from the amino acid mass table.
* cyclic_subpeptides(peptide): Generates all cyclic subpeptides from the given peptide.
* theoretical_spectrum(peptide): Calculates and returns the sorted theoretical spectrum of the cyclic peptide.

# Applications
* Predicting theoretical mass spectra for cyclic peptides in mass spectrometry.
* Supporting peptide identification and sequencing workflows.
* Educational tool for understanding peptide fragmentation patterns.

# License
This project is licensed under the MIT License.

