/*
 * Please fill the functions in this file.
 * You can add additional functions. 
 *
 * Hint: 
 * You can write additonal functions.
 * You can test your functions with your own input file.
 * See details in README or typing command ./pa04 in terminal after make.
 * See output format examples in any of the files in directory expected.
 * 
 * You may create additional arrays if needed.  The maximum size
 * needed is specified by MAXLENGTH in pa04.h.
 */

#include "pa04.h"
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

/*
 * =================================================================
 * This function prints all partitions of a positive integer value
 * For example, if the value is 3:
 *
 * partitionAll 3
 * = 1 + 1 + 1
 * = 1 + 2
 * = 2 + 1
 * = 3
 */

void printPartition(int * part, int length)
{
	printf("= ");
	int index;
		for (index = 0; index < length - 1; index ++)
		{
			printf("%d + ", part[index]);
		}
	printf("%d\n", part[length - 1]);
}

void partition(int * part, int index, int left)
{
  int value;
  if (left == 0)
  {
	  printPartition(part, index);
	  return;
  }
  for (value = 1; value <= left; value++)
  {
	  part[index] = value;
	  partition(part, index + 1, left - value);
  }
}

void partitionAll(int value)
{
	int * part;
	part = malloc(sizeof(int) * value);
	printf("partitionAll %d\n", value);
	partition(part, 0, value);
	free(part);
}
/*
 * =================================================================
 * This function prints the partitions that use increasing values.
 *
 * For example, if value is 5
 * 2 + 3 and
 * 1 + 4 are valid partitions
 *
 * 5 is a valid partition
 * 
 * 1 + 1 + 3 and
 * 2 + 1 + 2 and
 * 3 + 2 are invalid partitions.
 * 
 * The program should generate only valid partitions.  Do not
 * generates invalid partitions and checks validity before printing.
 *
 */
void partitionIncHelp(int * part, int index, int left)
{
  int value;
  
  if (left == 0)
  {
	  printPartition(part, index);
	  return;
  }
  for (value = 1; value <= left; value++)
  {
	  part[index] = value;
	  if(index == 0)
	  {
		  partitionIncHelp(part, 1, left - value);
	  }
	  else if (part[index-1] < value)
		{
			partitionIncHelp(part, index + 1, left - value);
		}
  }
}

void partitionIncreasing(int value)
{
	int * part;
	part = malloc(sizeof(int) * value);
	printf("partitionIncreasing %d\n", value);
  	partitionIncHelp(part, 0, value);
	free(part);
}

/*
 * =================================================================
 * This function prints the partitions that use Decreasing values.
 *
 * For example, if value is 5
 * 3 + 2 and
 * 4 + 1 are valid partitions
 *
 * 5 is a valid partition
 * 
 * 1 + 1 + 3 and
 * 2 + 1 + 2 and
 * 2 + 3 are invalid partitions.
 * 
 * The program should generate only valid partitions.  Do not
 * generates invalid partitions and checks validity before printing.
 *
 */
void partitionDecHelp(int * part, int index, int left)
{
  int value;
  
  if (left == 0)
  {
	  printPartition(part, index);
	  return;
  }
  for (value = 1; value <= left; value++)
  {
	  part[index] = value;
	  /*if(index == 0)
	  {
		  partitionDecHelp(part, left, left - value);
	  }
	  else if(part[index - 1] > value)
		{
			partitionDecHelp(part, index + 1, left - value);
		}*/
	  if(index == 0)
	  {
		  partitionDecHelp(part, 1, left - value);
	  }
	else if(part[index - 1] > value)
	{
			partitionDecHelp(part, index + 1, left - value);
	}
  }
}

void partitionDecreasing(int value)
{
	int * part;
	part = malloc(sizeof(int) * value);
    printf("partitionDecreasing %d\n", value);
    partitionDecHelp(part, 0, value);
	free(part);
}

/*
 * =================================================================
 * This function prints odd number only partitions of a positive integer value
 * For example, if value is 5
 * 1 + 1 + 1 + 1 + 1 and
 * 1 + 3 + 1 are valid partitions
 *
 * 5 is a valid partition
 * 
 * 1 + 1 + 1 + 2 and
 * 2 + 1 + 2 and
 * 2 + 3 are invalid partitions.
 * 
 * The program should generate only valid partitions.  Do not
 * generates invalid partitions and checks validity before printing.
 */
void partitionOddHelp(int * part, int index, int left)
{
  int value;
  
  if (left == 0)
  {
	  printPartition(part, index);
	  return;
  }
  for (value = 1; value <= left; value += 2)
  {
	  part[index] = value;
	  partitionOddHelp(part, index + 1, left - value);
  }
}

void partitionOdd(int value)
{
  int * part;
  part = malloc(sizeof(int) * value);
  printf("partitionOdd %d\n", value);
  partitionOddHelp(part, 0, value);
  free(part);
}

/*
 * =================================================================
 * This function prints even number only partitions of a positive integer value
 * For example, if value is 8
 * 2 + 2 + 2 + 2and
 * 2 + 4 + 2 are valid partitions
 *
 * 8 is a valid partition
 *
 * 2 + 1 + 1 + 2 + 2and
 * 2 + 1 + 2 + 3and
 * 5 + 3 are invalid partitions.
 *
 * if the value is 5, there will be no result generated
 * 
 * The program should generate only valid partitions.  Do not
 * generates invalid partitions and checks validity before printing.
 */
void partitionEvenHelp(int * part, int index, int left)
{
  int value;
  
  if (left == 0)
  {
	  printPartition(part, index);
	  return;
  }
  for (value = 2; value <= left; value +=2)
  {
	  part[index] = value;
	  partitionEvenHelp(part, index + 1, left - value);
  }
}

void partitionEven(int value)
{
  int * part;
  part = malloc(sizeof(int) * value);
  printf("partitionEven %d\n", value);
  partitionEvenHelp(part, 0, value);
  free(part);
}

/*
 * =================================================================
 * This function prints alternate ood and even number partitions of a positive integer value. Each partition starts from and odd number, even number, ood number again, even number again...etc.
 *
 * For example, if value is 6
 * 1 + 2 + 1 + 2 and
 * 3 + 2 + 1 are valid partitions
 *
 * 6 is not a valid partition
 *
 * 2 + 1 + 1 + 2 and
 * 2 + 1 + 3and
 * 5 + 1 are invalid partitions.
 * 
 * The program should generate only valid partitions.  Do not
 * generates invalid partitions and checks validity before printing.
 */

void partitionOddAndEvenHelp(int * part, int index, int left)
{
  int value;
  
  if (left == 0)
  {
	  printPartition(part, index);
	  return;
  }
  for (value = 2; value <= left; value +=2)
  {
	  part[index] = value;
	  partitionOddAndEvenHelp(part, index + 1, left - value);
  }
}

void partitionOddAndEven(int value)
{
  int * part;
  part = malloc(sizeof(int) * value);
  printf("partitionOddAndEven %d\n", value);
  partitionPrimeHelp(part, 0, value);
  free(part);
}

/*
 * =================================================================
 * This function prints prime number only partitions of a positive integer value
 * For example, if value is 6
 * 2 + 2 + 2 and
 * 3 + 3 are valid partitions
 *
 * 6 is not a valid partition
 * 
 * 2 + 4 and
 * 1 + 5 are invalid partitions.
 * 
 * The program should generate only valid partitions.  Do not
 * generates invalid partitions and checks validity before printing.
 */
int primetest(int value)
{
	if(value % 2 == 0)
	{
		return 0;
	}
	
	int i;
	int max;
	
	max = floor(sqrt(value));
	
	for(i = 2; i < max; i++)
	{
		if(value % ((2 * i) + 1) == 0)
		{
			return 0;
		}
	}
	return 1;
}

void partitionPrimeHelp(int * part, int index, int left)
{
  int value;
  int test = 0;
  
  if (left == 0)
  {
	  printPartition(part, index);
	  return;
  }
  for (value = 2; value <= left; value++)
  //for (value = left; value > left; value--)
  {
	  part[index] = value;
	  test = primetest(value);
	  
	  if(test != 0)
	  {
		partitionPrimeHelp(part, index += 1, left - value);
	  }
	  else
	  {
		  return;
	  }
  }
}

void partitionPrime(int value)
{
  int * part;
  part = malloc(sizeof(int) * value);
  printf("partitionPrime %d\n", value);
  partitionPrimeHelp(part, 0, value);
  free(part);
}
