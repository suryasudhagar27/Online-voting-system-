#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_CANDIDATES 10
#define MAX_VOTERS 100

// Structure to represent a candidate
typedef struct {
    int id;
    char name[50];
    int votes;
} Candidate;

// Array to store candidate information
Candidate candidates[MAX_CANDIDATES];

// Function prototypes
void initializeCandidates();
void printCandidates();
void vote();
void showResults();

int main() {
    int choice;

    initializeCandidates();

    do {
        printf("\nOnline Voting System\n");
        printf("1. Vote\n");
        printf("2. Show Results\n");
        printf("3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                vote();
                break;
            case 2:
                showResults();
                break;
            case 3:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    } while (choice != 3);

    return 0;
}

// Initialize candidates with some sample data
void initializeCandidates() {
    candidates[0].id = 1;
    strcpy(candidates[0].name, "Candidate 1");
    candidates[0].votes = 0;

    candidates¹.id = 2;
    strcpy(candidates¹.name, "Candidate 2");
    candidates¹.votes = 0;

    // Add more candidates as needed
}

// Print the list of candidates
void printCandidates() {
    printf("\nList of Candidates:\n");
    for (int i = 0; i < MAX_CANDIDATES; i++) {
        if (candidates[i].id != 0) {
            printf("%d. %s\n", candidates[i].id, candidates[i].name);
        }
    }
}

// Function to cast a vote
void vote() {
    int choice;
    printCandidates();
    printf("Enter the candidate ID you want to vote for: ");
    scanf("%d", &choice);

    for (int i = 0; i < MAX_CANDIDATES; i++) {
        if (candidates[i].id == choice) {
            candidates[i].votes++;
            printf("Vote cast successfully!\n");
            return;
        }
    }

    printf("Invalid candidate ID. Please try again.\n");
}

// Function to display voting results
void showResults() {
    printf("\nVoting Results:\n");
    for (int i = 0; i < MAX_CANDIDATES; i++) {
        if (candidates[i].id != 0) {
            printf("%s: %d votes\n", candidates[i].name, candidates[i].votes);
        }
    }
