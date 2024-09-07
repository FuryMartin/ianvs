# Fixed Quick Guide for Singletask Learning Bench

## Step.1 Ianvs preparation

```bash
# Create a new conda environment
conda create -n ianvs-py36 python=3.6
conda activate ianvs-py36

# Clone path-error-fixed Ianvs
git clone https://github.com/FuryMartin/ianvs.git
# switch to quickstart branch
git switch quickstart 
cd ianvs

# Download dependency-error-fixed Sedna
wget https://github.com/FuryMartin/sedna/releases/download/v0.4.1.1/sedna-0.4.1.1-py3-none-any.whl
pip install sedna-0.4.1.1-py3-none-any.whl

pip install -r requirements.txt

```

## Step.2 PCB-AoI Example Environment Preparation

```bash
pip install examples/resources/algorithms/FPN_TensorFlow-0.1-py3-none-any.whl

# install cv2(opencv-python)
sudo apt-get update
sudo apt-get install libgl1-mesa-glx  # This is needed by cv2(opencv-python)

pip install opencv-python~=3.4 # must be under 4.0, otherwise it will build from source with a long time
```

## Step.3 Dataset and Model Preparation

```bash
# be sure to be in ianvs root path

mkdir dataset
cd dataset
wget https://kubeedge.obs.cn-north-1.myhuaweicloud.com:443/ianvs/pcb-aoi/dataset.zip
unzip dataset.zip

cd .. # back to ianvs root path

mkdir initial_model
cd initial_model
wget https://kubeedge.obs.cn-north-1.myhuaweicloud.com:443/ianvs/pcb-aoi/model.zip # No need to unzip
```

## Step.4 Run PCB-AoI

```bash
$ python benchmarking.py -f ./examples/pcb-aoi/singletask_learning_bench/fault detection/benchmarkingjob.yaml

/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/framework/dtypes.py:516: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_qint8 = np.dtype([("qint8", np.int8, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/framework/dtypes.py:517: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_quint8 = np.dtype([("quint8", np.uint8, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/framework/dtypes.py:518: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_qint16 = np.dtype([("qint16", np.int16, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/framework/dtypes.py:519: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_quint16 = np.dtype([("quint16", np.uint16, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/framework/dtypes.py:520: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_qint32 = np.dtype([("qint32", np.int32, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/framework/dtypes.py:525: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  np_resource = np.dtype([("resource", np.ubyte, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorboard/compat/tensorflow_stub/dtypes.py:541: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_qint8 = np.dtype([("qint8", np.int8, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorboard/compat/tensorflow_stub/dtypes.py:542: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_quint8 = np.dtype([("quint8", np.uint8, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorboard/compat/tensorflow_stub/dtypes.py:543: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_qint16 = np.dtype([("qint16", np.int16, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorboard/compat/tensorflow_stub/dtypes.py:544: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_quint16 = np.dtype([("quint16", np.uint16, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorboard/compat/tensorflow_stub/dtypes.py:545: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  _np_qint32 = np.dtype([("qint32", np.int32, 1)])
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorboard/compat/tensorflow_stub/dtypes.py:550: FutureWarning: Passing (type, 1) or '1type' as a synonym of type is deprecated; in a future version of numpy, it will be understood as (type, (1,)) / '(1,)type'.
  np_resource = np.dtype([("resource", np.ubyte, 1)])
173 in train...
Conversion progress:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]100%      173/173
Conversion is completed!
tfrecord path is --> /tmp/tmprvz0e58k/user_temporary_train.tfrecord
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/ops/gradients_util.py:93: UserWarning: Converting sparse IndexedSlices to a dense Tensor of unknown shape. This may consume a large amount of memory.
  "Converting sparse IndexedSlices to a dense Tensor of unknown shape. "
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/ops/gradients_util.py:93: UserWarning: Converting sparse IndexedSlices to a dense Tensor of unknown shape. This may consume a large amount of memory.
  "Converting sparse IndexedSlices to a dense Tensor of unknown shape. "
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/ops/gradients_util.py:93: UserWarning: Converting sparse IndexedSlices to a dense Tensor of unknown shape. This may consume a large amount of memory.
  "Converting sparse IndexedSlices to a dense Tensor of unknown shape. "
2024-09-07 13:15:14.562910: I tensorflow/core/platform/cpu_feature_guard.cc:142] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA
2024-09-07 13:15:14.573158: I tensorflow/core/platform/profile_utils/cpu_utils.cc:94] CPU Frequency: 2894465000 Hz
2024-09-07 13:15:14.576940: I tensorflow/compiler/xla/service/service.cc:168] XLA service 0x561f06e77760 executing computations on platform Host. Devices:
2024-09-07 13:15:14.577010: I tensorflow/compiler/xla/service/service.cc:175]   StreamExecutor device (0): <undefined>, <undefined>
2024-09-07 13:15:17.096915: W tensorflow/compiler/jit/mark_for_compilation_pass.cc:1412] (One-time warning): Not using XLA:CPU for cluster because envvar TF_XLA_FLAGS=--tf_xla_cpu_global_jit was not set.  If you want XLA:CPU, either set that envvar, or use experimental_jit_scope to enable XLA:CPU.  To confirm that XLA is active, pass --vmodule=xla_compilation_cache=1 (as a proper command-line flag, not via TF_XLA_FLAGS) or set the envvar XLA_FLAGS=--xla_hlo_profile.
restore model
2024-09-07 13:15:29.528993: W tensorflow/core/framework/allocator.cc:107] Allocation of 201707520 exceeds 10% of system memory.
2024-09-07 13:15:31.043421: W tensorflow/core/framework/allocator.cc:107] Allocation of 235929600 exceeds 10% of system memory.
2024-09-07 13:15:31.049286: W tensorflow/core/framework/allocator.cc:107] Allocation of 235929600 exceeds 10% of system memory.
2024-09-07 13:15:31.423223: W tensorflow/core/framework/allocator.cc:107] Allocation of 235929600 exceeds 10% of system memory.
2024-09-07 13:15:31.423233: W tensorflow/core/framework/allocator.cc:107] Allocation of 235929600 exceeds 10% of system memory.
2024-09-07 13:15:22: step50001 image_name:b'20161019-SPI-AOI-1.jpeg'
                             rpn_loc_loss:0.0033 | rpn_cla_loss:0.0005 | rpn_total_loss:0.0038
                             fast_rcnn_loc_loss:0.0130 | fast_rcnn_cla_loss:0.0049 | fast_rcnn_total_loss:0.0179
                             added_loss:0.0217 | total_loss:0.6604 | pre_cost_time:11.9198s
Weights have been saved to /tmp/tmpfvcks5ij/user_50005_1725686158.5898027_model.ckpt.
20170314-SPI-AOI-1.jpeg cost 1.8992695808410645s:[                                        ]2%   1/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170316-SPI-AOI-19.jpeg cost 1.24312424659729s:[>                                       ]4%    2/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170321-SPI-AOI-3.jpeg cost 1.174713373184204s:[>>                                      ]5%    3/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170324-SPI-AOI-4.jpeg cost 1.1722195148468018s:[>>                                      ]7%   4/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170330-SPI-AOI-10.jpeg cost 1.2106575965881348s:[>>>                                     ]9%  5/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170406-SPI-AOI-4.jpeg cost 1.233936071395874s:[>>>>                                    ]10%   6/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170407-SPI-AOI-3.jpeg cost 1.2204406261444092s:[>>>>                                    ]12%  7/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170408-SPI-AOI-3.jpeg cost 1.1502025127410889s:[>>>>>                                   ]14%  8/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170421-SPI-AOI-2.jpeg cost 1.1404049396514893s:[>>>>>>                                  ]15%  9/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170515-SPI-AOI-3.jpeg cost 1.1250994205474854s:[>>>>>>                                  ]17%  10/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170601-SPI-AOI-2.jpeg cost 1.397139072418213s:[>>>>>>>                                 ]19%   11/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170610-SPI-AOI-1.jpeg cost 1.366004467010498s:[>>>>>>>>                                ]20%   12/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170615-SPI-AOI-3.jpeg cost 1.3599693775177002s:[>>>>>>>>                                ]22%  13/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170617-SPI-AOI-2.jpeg cost 1.269425630569458s:[>>>>>>>>>                               ]24%   14/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170619-SPI-AOI-4.jpeg cost 1.2409145832061768s:[>>>>>>>>>>                              ]25%  15/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170620-SPI-AOI-1.jpeg cost 1.1568052768707275s:[>>>>>>>>>>                              ]27%  16/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170705-SPI-AOI-1.jpeg cost 1.2021150588989258s:[>>>>>>>>>>>                             ]29%  17/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170705-SPI-AOI-2.jpeg cost 1.1560466289520264s:[>>>>>>>>>>>>                            ]30%  18/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170705-SPI-AOI-3.jpeg cost 1.1935484409332275s:[>>>>>>>>>>>>                            ]32%  19/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170731-SPI-AOI-5.jpeg cost 1.166513204574585s:[>>>>>>>>>>>>>                           ]34%   20/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170814-SPI-AOI-1.jpeg cost 1.1634328365325928s:[>>>>>>>>>>>>>>                          ]35%  21/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170815-SPI-AOI-1.jpeg cost 1.1472158432006836s:[>>>>>>>>>>>>>>                          ]37%  22/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170815-SPI-AOI-2.jpeg cost 1.1456372737884521s:[>>>>>>>>>>>>>>>                         ]39%  23/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170829-SPI-AOI-3.jpeg cost 1.1998364925384521s:[>>>>>>>>>>>>>>>>                        ]40%  24/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170830-SPI-AOI-1.jpeg cost 1.1431527137756348s:[>>>>>>>>>>>>>>>>                        ]42%  25/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170901-SPI-AOI-1.jpeg cost 1.1480259895324707s:[>>>>>>>>>>>>>>>>>                       ]44%  26/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170912-SPI-AOI-4.jpeg cost 1.1337640285491943s:[>>>>>>>>>>>>>>>>>>                      ]45%  27/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171017-SPI-AOI-1.jpeg cost 1.1526079177856445s:[>>>>>>>>>>>>>>>>>>                      ]47%  28/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171109-SPI-AOI-10.jpeg cost 1.1722972393035889s:[>>>>>>>>>>>>>>>>>>>                     ]49% 29/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171109-SPI-AOI-9.jpeg cost 1.2924814224243164s:[>>>>>>>>>>>>>>>>>>>>                    ]50%  30/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-1.jpeg cost 1.1753578186035156s:[>>>>>>>>>>>>>>>>>>>>                    ]52%  31/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-2.jpeg cost 1.1450302600860596s:[>>>>>>>>>>>>>>>>>>>>>                   ]54%  32/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-3.jpeg cost 1.1343891620635986s:[>>>>>>>>>>>>>>>>>>>>>>                  ]56%  33/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-6.jpeg cost 1.1418054103851318s:[>>>>>>>>>>>>>>>>>>>>>>                  ]57%  34/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-8.jpeg cost 1.144888162612915s:[>>>>>>>>>>>>>>>>>>>>>>>                 ]59%   35/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-9.jpeg cost 1.1466848850250244s:[>>>>>>>>>>>>>>>>>>>>>>>>                ]60%  36/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171206-SPI-AOI-6.jpeg cost 1.2449729442596436s:[>>>>>>>>>>>>>>>>>>>>>>>>                ]62%  37/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171206-SPI-AOI-7.jpeg cost 1.1631956100463867s:[>>>>>>>>>>>>>>>>>>>>>>>>>               ]64%  38/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171207-SPI-AOI-3.jpeg cost 1.164674997329712s:[>>>>>>>>>>>>>>>>>>>>>>>>>>              ]65%   39/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171207-SPI-AOI-4.jpeg cost 1.0954980850219727s:[>>>>>>>>>>>>>>>>>>>>>>>>>>              ]67%  40/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171227-SPI-AOI-3.jpeg cost 1.1651890277862549s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>             ]69%  41/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180102-SPI-AOI-1.jpeg cost 1.2061455249786377s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>            ]70%  42/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180108-SPI-AOI-12.jpeg cost 1.1391501426696777s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>            ]72% 43/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180124-SPI-AOI-2.jpeg cost 1.1846628189086914s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>           ]74%  44/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180206-SPI-AOI-3.jpeg cost 1.1373827457427979s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>          ]75%  45/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180309-SPI-AOI-15.jpeg cost 1.1784496307373047s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>          ]77% 46/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180309-SPI-AOI-17.jpeg cost 1.1840851306915283s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>         ]79% 47/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180315-SPI-AOI-1.jpeg cost 1.1996138095855713s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>        ]80%  48/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180319-SPI-AOI-4.jpeg cost 1.1549370288848877s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>        ]82%  49/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180322-SPI-AOI-8.jpeg cost 1.2007989883422852s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>       ]84%  50/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180403-SPI-AOI-1.jpeg cost 1.1770670413970947s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>      ]85%  51/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180403-SPI-AOI-2.jpeg cost 1.1236793994903564s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>      ]87%  52/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180403-SPI-AOI-3.jpeg cost 1.1026599407196045s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>     ]89%  53/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180427-SPI-AOI-1.jpeg cost 1.113171100616455s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>    ]90%   54/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180503-SPI-AOI-10.jpeg cost 1.2007012367248535s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>    ]92% 55/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180514-SPI-AOI-1.jpeg cost 1.1436052322387695s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>   ]94%  56/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180523-SPI-AOI-1.jpeg cost 1.14377760887146s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>  ]95%    57/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180523-SPI-AOI-2.jpeg cost 1.1312873363494873s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>  ]97%  58/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180524-SPI-AOI-1.jpeg cost 1.2331018447875977s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>> ]99%  59/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180601-SPI-AOI-2.jpeg cost 1.1350293159484863s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]100% 60/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
60 in train...
Conversion progress:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]100%      60/60
Conversion is completed!
tfrecord path is --> /tmp/tmpyij25jdo/user_temporary_test.tfrecord
f1_score_avg: 0.8488
173 in train...
Conversion progress:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]100%      173/173
Conversion is completed!
tfrecord path is --> /tmp/tmpvve_xe7q/user_temporary_train.tfrecord
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/ops/gradients_util.py:93: UserWarning: Converting sparse IndexedSlices to a dense Tensor of unknown shape. This may consume a large amount of memory.
  "Converting sparse IndexedSlices to a dense Tensor of unknown shape. "
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/ops/gradients_util.py:93: UserWarning: Converting sparse IndexedSlices to a dense Tensor of unknown shape. This may consume a large amount of memory.
  "Converting sparse IndexedSlices to a dense Tensor of unknown shape. "
/home/fury/miniconda3/envs/py36/lib/python3.6/site-packages/tensorflow/python/ops/gradients_util.py:93: UserWarning: Converting sparse IndexedSlices to a dense Tensor of unknown shape. This may consume a large amount of memory.
  "Converting sparse IndexedSlices to a dense Tensor of unknown shape. "
restore model
2024-09-07 13:18:21: step50001 image_name:b'20161019-SPI-AOI-1.jpeg'
                             rpn_loc_loss:0.0049 | rpn_cla_loss:0.0009 | rpn_total_loss:0.0058
                             fast_rcnn_loc_loss:0.0123 | fast_rcnn_cla_loss:0.0016 | fast_rcnn_total_loss:0.0139
                             added_loss:0.0196 | total_loss:0.6584 | pre_cost_time:11.7905s
Weights have been saved to /tmp/tmpf94damgg/user_50005_1725686338.8320968_model.ckpt.
20170314-SPI-AOI-1.jpeg cost 1.9877476692199707s:[                                        ]2%   1/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170316-SPI-AOI-19.jpeg cost 1.1667096614837646s:[>                                       ]4%  2/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170321-SPI-AOI-3.jpeg cost 1.1998815536499023s:[>>                                      ]5%   3/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170324-SPI-AOI-4.jpeg cost 1.1965484619140625s:[>>                                      ]7%   4/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170330-SPI-AOI-10.jpeg cost 1.2063465118408203s:[>>>                                     ]9%  5/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170406-SPI-AOI-4.jpeg cost 1.1119236946105957s:[>>>>                                    ]10%  6/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170407-SPI-AOI-3.jpeg cost 1.1064987182617188s:[>>>>                                    ]12%  7/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170408-SPI-AOI-3.jpeg cost 1.1125373840332031s:[>>>>>                                   ]14%  8/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170421-SPI-AOI-2.jpeg cost 1.1709821224212646s:[>>>>>>                                  ]15%  9/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170515-SPI-AOI-3.jpeg cost 1.1106574535369873s:[>>>>>>                                  ]17%  10/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170601-SPI-AOI-2.jpeg cost 1.252490520477295s:[>>>>>>>                                 ]19%   11/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170610-SPI-AOI-1.jpeg cost 1.189293622970581s:[>>>>>>>>                                ]20%   12/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170615-SPI-AOI-3.jpeg cost 1.2054498195648193s:[>>>>>>>>                                ]22%  13/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170617-SPI-AOI-2.jpeg cost 1.1722197532653809s:[>>>>>>>>>                               ]24%  14/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170619-SPI-AOI-4.jpeg cost 1.1441588401794434s:[>>>>>>>>>>                              ]25%  15/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170620-SPI-AOI-1.jpeg cost 1.2177774906158447s:[>>>>>>>>>>                              ]27%  16/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170705-SPI-AOI-1.jpeg cost 1.1724419593811035s:[>>>>>>>>>>>                             ]29%  17/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170705-SPI-AOI-2.jpeg cost 1.1207973957061768s:[>>>>>>>>>>>>                            ]30%  18/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170705-SPI-AOI-3.jpeg cost 1.0955514907836914s:[>>>>>>>>>>>>                            ]32%  19/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170731-SPI-AOI-5.jpeg cost 1.13456130027771s:[>>>>>>>>>>>>>                           ]34%    20/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170814-SPI-AOI-1.jpeg cost 1.097208023071289s:[>>>>>>>>>>>>>>                          ]35%   21/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170815-SPI-AOI-1.jpeg cost 1.1990149021148682s:[>>>>>>>>>>>>>>                          ]37%  22/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170815-SPI-AOI-2.jpeg cost 1.1004934310913086s:[>>>>>>>>>>>>>>>                         ]39%  23/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170829-SPI-AOI-3.jpeg cost 1.1494488716125488s:[>>>>>>>>>>>>>>>>                        ]40%  24/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170830-SPI-AOI-1.jpeg cost 1.1859540939331055s:[>>>>>>>>>>>>>>>>                        ]42%  25/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170901-SPI-AOI-1.jpeg cost 1.1006627082824707s:[>>>>>>>>>>>>>>>>>                       ]44%  26/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20170912-SPI-AOI-4.jpeg cost 1.1548023223876953s:[>>>>>>>>>>>>>>>>>>                      ]45%  27/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171017-SPI-AOI-1.jpeg cost 1.1213669776916504s:[>>>>>>>>>>>>>>>>>>                      ]47%  28/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171109-SPI-AOI-10.jpeg cost 1.1192359924316406s:[>>>>>>>>>>>>>>>>>>>                     ]49% 29/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171109-SPI-AOI-9.jpeg cost 1.108816385269165s:[>>>>>>>>>>>>>>>>>>>>                    ]50%   30/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-1.jpeg cost 1.1492056846618652s:[>>>>>>>>>>>>>>>>>>>>                    ]52%  31/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-2.jpeg cost 1.1037437915802002s:[>>>>>>>>>>>>>>>>>>>>>                   ]54%  32/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-3.jpeg cost 1.1987888813018799s:[>>>>>>>>>>>>>>>>>>>>>>                  ]56%  33/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-6.jpeg cost 1.1624577045440674s:[>>>>>>>>>>>>>>>>>>>>>>                  ]57%  34/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-8.jpeg cost 1.170893907546997s:[>>>>>>>>>>>>>>>>>>>>>>>                 ]59%   35/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171110-SPI-AOI-9.jpeg cost 1.101893663406372s:[>>>>>>>>>>>>>>>>>>>>>>>>                ]60%   36/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171206-SPI-AOI-6.jpeg cost 1.1074655055999756s:[>>>>>>>>>>>>>>>>>>>>>>>>                ]62%  37/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171206-SPI-AOI-7.jpeg cost 1.147256851196289s:[>>>>>>>>>>>>>>>>>>>>>>>>>               ]64%   38/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171207-SPI-AOI-3.jpeg cost 1.2299110889434814s:[>>>>>>>>>>>>>>>>>>>>>>>>>>              ]65%  39/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171207-SPI-AOI-4.jpeg cost 1.2346913814544678s:[>>>>>>>>>>>>>>>>>>>>>>>>>>              ]67%  40/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20171227-SPI-AOI-3.jpeg cost 1.2504644393920898s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>             ]69%  41/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180102-SPI-AOI-1.jpeg cost 1.1625089645385742s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>            ]70%  42/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180108-SPI-AOI-12.jpeg cost 1.2971489429473877s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>            ]72% 43/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180124-SPI-AOI-2.jpeg cost 1.1921966075897217s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>           ]74%  44/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180206-SPI-AOI-3.jpeg cost 1.217939853668213s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>          ]75%   45/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180309-SPI-AOI-15.jpeg cost 1.151287317276001s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>          ]77%  46/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180309-SPI-AOI-17.jpeg cost 1.1163346767425537s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>         ]79% 47/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180315-SPI-AOI-1.jpeg cost 1.190739631652832s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>        ]80%   48/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180319-SPI-AOI-4.jpeg cost 1.1760311126708984s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>        ]82%  49/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180322-SPI-AOI-8.jpeg cost 1.1979146003723145s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>       ]84%  50/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180403-SPI-AOI-1.jpeg cost 1.2143208980560303s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>      ]85%  51/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180403-SPI-AOI-2.jpeg cost 1.2253997325897217s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>      ]87%  52/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180403-SPI-AOI-3.jpeg cost 1.1368117332458496s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>     ]89%  53/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180427-SPI-AOI-1.jpeg cost 1.1583764553070068s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>    ]90%  54/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180503-SPI-AOI-10.jpeg cost 1.1754961013793945s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>    ]92% 55/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180514-SPI-AOI-1.jpeg cost 1.2869431972503662s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>   ]94%  56/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180523-SPI-AOI-1.jpeg cost 1.145683765411377s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>  ]95%   57/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180523-SPI-AOI-2.jpeg cost 1.1010451316833496s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>  ]97%  58/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180524-SPI-AOI-1.jpeg cost 1.2081241607666016s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>> ]99%  59/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
20180601-SPI-AOI-2.jpeg cost 1.1560626029968262s:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]100% 60/60
Inference results have been saved to directory:./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c/output/inference/.
60 in train...
Conversion progress:[>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]100%      60/60
Conversion is completed!
tfrecord path is --> /tmp/tmpw98tc1gs/user_temporary_test.tfrecord
f1_score_avg: 0.8699
/home/fury/Code/ianvs-version/ianvs/core/storymanager/rank/rank.py:178: FutureWarning: The pandas.np module is deprecated and will be removed from pandas in a future version. Import numpy directly instead
  all_df.index = pd.np.arange(1, len(all_df) + 1)
/home/fury/Code/ianvs-version/ianvs/core/storymanager/rank/rank.py:208: FutureWarning: The pandas.np module is deprecated and will be removed from pandas in a future version. Import numpy directly instead
  selected_df.index = pd.np.arange(1, len(selected_df) + 1)

+------+-------------------------+----------+--------------------+-----------+--------------------+-------------------------+---------------------+------------------------------------------------------------------------------------------+
| rank |        algorithm        | f1_score |      paradigm      | basemodel | basemodel-momentum | basemodel-learning_rate |         time        |                                           url                                            |
+------+-------------------------+----------+--------------------+-----------+--------------------+-------------------------+---------------------+------------------------------------------------------------------------------------------+
|  1   | fpn_singletask_learning |  0.8699  | singletasklearning |    FPN    |        0.5         |           0.1           | 2024-09-07 13:20:49 | ./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c89-6cd8-11ef-87fe-cfc3c41a8e6c |
|  2   | fpn_singletask_learning |  0.8488  | singletasklearning |    FPN    |        0.95        |           0.1           | 2024-09-07 13:17:51 | ./workspace/benchmarkingjob/fpn_singletask_learning/1b1f5c88-6cd8-11ef-87fe-cfc3c41a8e6c |
|  3   |                         |          |                    |           |                    |                         |                     |                                                                                          |
+------+-------------------------+----------+--------------------+-----------+--------------------+-------------------------+---------------------+------------------------------------------------------------------------------------------+


```

Now you finish PCB-AoI's SingleTaskLearning Example.
