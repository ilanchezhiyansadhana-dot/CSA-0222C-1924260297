#include <stdio.h>
#include <string.h>

struct date {
    int day, month, year;
};

struct bp {
    int systolic, diastolic;
};

struct patient {
    char name[30];
    int age;
    char phone[11];
    struct bp pressure;
    struct date visit;
};

void addPatient(struct patient *p, char n[], int a,
                char ph[], int s, int d,
                int day, int month, int year) {
    strcpy(p->name, n);
    p->age = a;
    strcpy(p->phone, ph);
    p->pressure.systolic = s;
    p->pressure.diastolic = d;
    p->visit.day = day;
    p->visit.month = month;
    p->visit.year = year;
}

int main() {
    struct patient p;

    addPatient(&p, "Arun", 25, "9876543210",
               120, 80, 21, 11, 2026);

    printf("Patient Details\n");
    printf("Name: %s\n", p.name);
    printf("Age: %d\n", p.age);
    printf("Phone: %s\n", p.phone);
    printf("Blood Pressure: %d/%d\n",
           p.pressure.systolic,
           p.pressure.diastolic);
    printf("Visit Date: %02d/%02d/%d\n",
           p.visit.day, p.visit.month, p.visit.year);

    return 0;
}# CSA-0222C-1924260297