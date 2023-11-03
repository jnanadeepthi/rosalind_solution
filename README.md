# rosalind_solution
Here are the solution code for rosalind bioinformaitcs questions
#Gc_count
def gc_count():
    n = int(input())
    sequences = []

    # Read the sequences
    for _ in range(n):
        seq = input().split()
        accession_id = seq[0]
        sequence = ''.join(filter(None, seq[1:]))
        sequences.append((accession_id, sequence))

    max_gc_id = ""
    max_gc_percentage = -1.0

    for accession_id, sequence in sequences:
        gc_count = sequence.count("G") + sequence.count("C")
        percentage_gc = (gc_count / len(sequence)) * 100

        if percentage_gc > max_gc_percentage:
            max_gc_percentage = percentage_gc
            max_gc_id = accession_id

    print(max_gc_id)
    print(f"{max_gc_percentage:.6f}")
