# code5
//快速排序  
void QuickSort(int* arr, int begin, int end)
{
	if (begin >= end)
		return;
	int left = begin;
	int right = end;
	int keyi = begin;
	while (begin < end)
	{
		while (arr[end] >= arr[keyi] && begin < end)
		{
			--end;
		}
		while (arr[begin] <= arr[keyi] && begin < end)
		{
			++begin;
		}
		swap(&arr[begin], &arr[end]);
	}
	swap(&arr[keyi], &arr[end]);
	keyi = end;
	QuickSort(arr, left, keyi - 1);
	QuickSort(arr,keyi + 1,right);
}
