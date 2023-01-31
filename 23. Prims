#include<stdio.h>
#include<stdlib.h>
#include<stdbool.h>
#define MAX 100
#define infinity 9999
#define NO_EDGE 0
int n;
int G[MAX][MAX];

int prim(int start) {
    int i, j, k, min_cost = 0;
    int distance[MAX], from[MAX], flag[MAX];

    for (i = 0; i < n; i++) {
        distance[i] = infinity;
        flag[i] = 0;
    }

    distance[start] = 0;
    from[start] = -1;

    for (i = 0; i < n; i++) {
        int min_distance = infinity, next_vertex = -1;
        for (j = 0; j < n; j++) {
            if (flag[j] == 0 && distance[j] < min_distance) {
                min_distance = distance[j];
                next_vertex = j;
            }
        }
        if (next_vertex == -1) {
            printf("Minimum spanning tree not possible\n");
            return 0;
        }
        flag[next_vertex] = 1;
        min_cost = min_cost + distance[next_vertex];
        for (j = 0; j < n; j++) {
            if (flag[j] == 0 && G[next_vertex][j] < distance[j]) {
                distance[j] = G[next_vertex][j];
                from[j] = next_vertex;
            }
        }
    }
    return min_cost;
}

int main() {
    int i, j, cost, start;
    printf("Enter number of vertices: ");
    scanf("%d", &n);
    printf("Enter the adjacency matrix:\n");
    for (i = 0; i < n; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &G[i][j]);
            if (G[i][j] == 0) {
                G[i][j] = infinity;
            }
        }
    }
    printf("Enter the starting vertex: ");
    scanf("%d", &start);
    cost = prim(start);
    printf("Minimum cost of the spanning tree = %d\n", cost);
    return 0;
}
