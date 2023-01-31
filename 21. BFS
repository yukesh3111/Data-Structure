#include <stdio.h>
#include <stdlib.h>
#define MAX_VERTICES 100
int n;
int adj_mat[MAX_VERTICES][MAX_VERTICES];
int queue[MAX_VERTICES];   
int front = 0;
int rear = -1;
void enqueue(int v) {
    queue[++rear] = v;
}
int dequeue() {
    return queue[front++];
}
int is_empty() {
    return front > rear;
}
void bfs(int start) {
    int v, w;
    int visited[MAX_VERTICES];
    for (v = 0; v < n; v++)
        visited[v] = 0;
    enqueue(start);
    visited[start] = 1;
    while (!is_empty()) {
        v = dequeue();
        printf("%d ", v);
        for (w = 0; w < n; w++)
            if (adj_mat[v][w] && !visited[w]) {
                enqueue(w);
                visited[w] = 1;
            }
    }
}
int main() {
    int i, j;
    int start;
    printf("Enter the number of vertices: ");
    scanf("%d", &n);
    printf("Enter the adjacency matrix: \n");
    for (i = 0; i < n; i++)
        for (j = 0; j < n; j++)
            scanf("%d", &adj_mat[i][j]);
    printf("Enter the starting vertex: ");
    scanf("%d", &start);
    printf("The breadth-first search traversal is: \n");
    bfs(start);
    return 0;
}
