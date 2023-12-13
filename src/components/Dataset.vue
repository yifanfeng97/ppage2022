<template>
  <v-container>
    <v-row class="text-center">
      <p class="text-h4">Released Datasets</p>
    </v-row>
    <v-row>
      <v-col cols="12" class="text-h6">OS-MN40 and OS-MN40-Miss</v-col>
      <v-col cols="12" class="text-body-1">
        <p>
          We released two datasets in SHREC'22 Track:
          <a class="text-decoration-none" href="https://www.moon-lab.tech/shrec22" target="_blank">Open-Set 3D Object
            Retrieval</a>. The objective of this track is to evaluate the performance of the
          different 3D shape retrieval algorithms under the Open-Set setting,
          which is an unknown-category shape retrieval task (each object
          contains multi-modal and multi-resolution representations: mesh, point
          cloud, voxel, and multi-view). In this setting, the retrieval and
          representation models are trained using known-category 3D objects and
          unknown-category 3D data are used for retrieval. This track includes
          two datasets, OS-MN40 and OS-MN40-Miss. Each object in OS-MN40 has
          complete four types of modalities and each object in OS-MN40-Miss
          contains incomplete data. Note that the two datasets are generated
          based on
          <a class="text-decoration-none" href="https://modelnet.cs.princeton.edu/" target="_blank">ModelNet40</a>. More
          details can be found
          <a class="text-decoration-none" href="https://www.moon-lab.tech/shrec22" target="_blank">here</a>.
        </p>
        <p>
          <strong>OS-MN40:</strong> An Open-Set 3D object retrieval dataset.
          Each 3D object in this dataset is represented with multi-modality and
          multi-resolution (1024 points and 2048 points for point cloud, 32
          times 32 times 32 resolution and 64 times 64 times 64 resolution for
          voxel, 24 views captured with 15 horizon interval cameras for
          multi-view and raw number face and simplified 500 faces for Mesh).
          Most objects in OS-MN40 are selected from the ModelNet40 dataset.
          OS-MN40 consists of 12309 objects from 40 classes. For each object, we
          provide four modalities (Point cloud, Voxel, Multi-view, and Mesh).
          Note that the dataset is collected for an open-set 3D retrieval
          setting. Thus, the categories in training and retrieval are not
          shared. Eight classes, including airplane, flower pot, glass box,
          keyboard, monitor, night stand, sink, and table, are selected for
          training. Other 32 classes, like bed, chair, plant, bathtub, and cup,
          are selected for retrieval, which are unknow-category in the training
          stage.
        </p>
        <p>
          <strong>OS-MN-40-Miss: </strong> This sub-dataset is constructed by
          random drop arbitrary modality with probability 0.4 for each object.
          OS-MN40-Miss is collected towards modality missing problem.
        </p>
        <p>
          <strong>Downloads: </strong>
          <a class="text-decoration-none" href="https://data.shrec22.moon-lab.tech:18443/SHREC22/OS-MN40.tar.gz"
            target="_blank">
            OS-MN40(~46G)</a>,
          <a class="text-decoration-none" href="https://data.shrec22.moon-lab.tech:18443/SHREC22/OS-MN40-Miss.tar.gz"
            target="_blank">OS-MN40-Miss(~28G)</a>,
          <a class="text-decoration-none" href="https://github.com/yifanfeng97/OS-MN40-Example" target="_blank">Example
            Code</a>.
        </p>
      </v-col>
      <v-col cols="12" class="d-flex justify-center">
        <v-img src="publication/2022-shrec22/fw.png" max-height="300" contain></v-img>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="text-h6">OS-ESB-core, OS-NTU-core and OS-MN40-core</v-col>
      <v-col cols="12" class="text-body-1">
        <p>
          Traditional 3D object recognition/classification
          task is more dependent on label information compared with the
          traditional 3D object retrieval task. In the 3D object
          recognition/classification task, a given 3D object must fall into
          a seen category, which significantly limits its applications in
          the real world. Here, we release three
          <a href="https://moon-lab.tech/os3dor/" target="_blank">open-set 3D
            object retrieval</a> datasets, OS-ESB-core, OS-NTU-core and OS-MN40-core.
          Each 3D object in the three datasets contains
          <span class="font-weight-black">three modalities</span>: multi-view,
          point cloud, and voxel. To compress the file size, in the multi-view
          modality, each image has the resolution of 256x256 without a
          transparent background. We place a plane below the 3D object. Thus,
          the shadow and depth information is valid in the three datasets. The
          voxel and point cloud modalities are directly extracted by
          <a href="http://www.open3d.org/" target="_blank">Open3D</a> refering
          to
          <a href="http://www.open3d.org/docs/release/python_api/open3d.geometry.VoxelGrid.html" target="_blank">here</a>
          and
          <a href="http://www.open3d.org/docs/0.7.0/python_api/open3d.geometry.sample_points_poisson_disk.html"
            target="_blank">here</a>, respectively. The format of the voxel data in the three datasets is
          ".ply", which can be analysed by the
          <a href="http://www.open3d.org/docs/release/python_api/open3d.geometry.VoxelGrid.html"
            target="_blank">open3d.io.read_voxel_grid</a>
          function. Those unit cooredinates of the voxel modality can be
          obtained by the
          <a href="http://www.open3d.org/docs/release/python_api/open3d.geometry.VoxelGrid.html"
            target="_blank">get_voxels</a>
          and
          <a href="http://www.open3d.org/docs/release/python_api/open3d.geometry.VoxelGrid.html"
            target="_blank">grid_index</a>
          functions. More details can refer to the
          <a href="https://github.com/yifanfeng97/OS3D/blob/main/datasets.py" target="_blank">dataloader</a>
          in
          <a href="https://github.com/yifanfeng97/OS3D" target="_blank">OS3D</a>.
        </p>
        <p>
          <span class="font-weight-black">OS-ESB-core:</span> Download links:
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-ESB-core/OS-ESB-core.zip"
            target="_blank">Multi-modal Data(~100M)</a>
          |
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-ESB-core/query_label.txt" target="_blank">Query
            Label</a>
          |
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-ESB-core/target_label.txt" target="_blank">Target
            Label</a>. This dataset contains usual engineering shapes from 41 categories
          like: handles, L Blocks, Oil Pans, etc.
        </p>
        <p>
          <span class="font-weight-black">OS-NTU-core:</span> Download links:
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-NTU-core/OS-NTU-core.zip"
            target="_blank">Multi-modal Data(~260M)</a>
          |
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-NTU-core/query_label.txt" target="_blank">Query
            Label</a>
          |
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-NTU-core/target_label.txt" target="_blank">Target
            Label</a>. This dataset contains 67 usual and unusual categories like: duck,
          ring, tank, hammer, etc.
        </p>
        <p>
          <span class="font-weight-black">OS-MN40-core:</span> Download links:
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-MN40-core/OS-MN40-core.zip"
            target="_blank">Multi-modal Data(~1.9G)</a>
          |
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-MN40-core/query_label.txt" target="_blank">Query
            Label</a>
          |
          <a href="https://data.shrec22.moon-lab.tech:18443/OS-3DOR/OS-MN40-core/target_label.txt" target="_blank">Target
            Label</a>. This dataset contains 40 usual categories like: bed, chair, etc.
        </p>
      </v-col>
    </v-row>

    <v-row justify="center">
      <v-col cols="12" md="6">
        <v-card class="pt-6">
          <!-- <h3>OS-ESB-core</h3> -->
          <v-img :src="require('../assets/datasets/vis_esb.jpg')" class="my-3" aspect-ratio="2.5" contain
            max-height="450" />
          <v-card-subtitle class="text-center font-italic text-subtitle-1 font-weight-medium">
            Visualization of the multi-modal representations of 3D objects in OS-ESB-core dataset
          </v-card-subtitle>
        </v-card>
      </v-col>

      <v-col cols="12" md="6">
        <v-card class="pt-6">
          <!-- <h3>OS-NTU-core</h3> -->
          <v-img :src="require('../assets/datasets/vis_ntu.jpg')" class="my-3" aspect-ratio="2.5" contain
            max-height="450" />
          <v-card-subtitle class="text-center font-italic text-subtitle-1 font-weight-medium">
            Visualization of the multi-modal representations of 3D objects in OS-NTU-core dataset
          </v-card-subtitle>
        </v-card>
      </v-col>

      <v-col cols="12" md="6">
        <v-card class="pt-6">
          <!-- <h3>OS-ESB-core</h3> -->
          <v-img :src="require('../assets/datasets/vis_mn40.jpg')" class="my-3" aspect-ratio="2.5" contain
            max-height="450" />
          <v-card-subtitle class="text-center font-italic text-subtitle-1 font-weight-medium">
            Visualization of the multi-modal representations of 3D objects in OS-MN40-core dataset
          </v-card-subtitle>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "MyDataset",

  data: () => ({}),
};
</script>
